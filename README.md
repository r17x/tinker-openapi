## Openapi basic command

> yarn gen generate -i <your-openapi-spec.yml|json|> -g <lang> -o <output> 
### Todo
- [ ] Make Generator base on openapi-generator
- [ ] Make Template for `Reason/Bucklescript/ReScript` (only for javascript target build)
- [ ] `PULL REQUEST YOUR TODO HERE`

### Reason / ReScript 

* http request implementation for (Javascript):
```reason
Js.Promise.(
      Fetch.fetch({j|https://api.github.com/users/$username|j})
      |> then_(Fetch.Response.json)
      |> then_(json =>
           switch (json->t_decode) {
           | Ok(result) => result |> resolve
           | Error(e) => DecodeError(e) |> raise |> reject
           }
         )
    );
```
* modeling:
> [@decco] is syntax extension for provide `decoder` & `encoder` function:
```
type t = {
    login: string,
    id: int,
    node_id: string,
    avatar_url: string,
    gravatar_id: string,
  };
```

