# Sample spec to reproduce CI lint error in multi file

Run `npm test` in terminal to see the lint errors


    ➜ npm test  
      
    > ci-lint@0.0.1 test  
    > spectral lint spec/**.yaml  
      
    OpenAPI 2.0 (Swagger) detected  
      
    ~/ci_lint/spec/index.yaml  
     1:1   warning  oas2-api-host          OpenAPI `host` must be present and non-empty string.  
     1:1   warning  openapi-tags           OpenAPI object should have non-empty `tags` array.  
    26:11  warning  operation-tag-defined  Operation tags should be defined in global tags.      paths./api/v2/tickets.get.tags[0]  
    40:11  warning  operation-tag-defined  Operation tags should be defined in global tags.      paths./api/v2/ticket/{ticket_id}.get.tags[0]  
      
    ~/ci_lint/spec/schemas/ticket.yaml  
     6:6   warning  fw-properties-underscore-case  Schema property `Id` should be in underscore case        properties.Id  
    11:12  warning  fw-properties-underscore-case  Schema property `subjec-t` should be in underscore case  properties.subjec-t  
      
    ✖ 6 problems (0 errors, 6 warnings, 0 infos, 0 hints)  



Compare it with the [warning annotations](https://github.com/ibrahimfw/ci-lint/pull/1/checks?check_run_id=3248730511) added by `stoplightio/spectral-action@v0.7.3` in [PR #1](https://github.com/ibrahimfw/ci-lint/pull/1)