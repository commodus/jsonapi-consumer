# JsonApi Client

Client framework for consuming JSONAPI APIs based on the JSON API standard (http://jsonapi.org/)

### Usage

#### Create HttpGet request with single response object
```
Response<Type[]> response = JsonApiConsumer.Get<Type>(
    baseURI: ABSOLUTE_URL,
    path: RELATIVE_URI,
    query: new Dictionary<string, string>() { { "FirstName", "Oktay" }, { "LastName", "Kır" } },
    headers: new Dictionary<string, string>() { { HEADER_API_KEY, HEADER_API_KEY_VALUE } } );
```

#### Create HttpGet request with array response object
```
Response<Type> response = JsonApiConsumer.GetById<Type>(
    id: "c833cbbf-7c81-4d30-b11a-88cf1c990b9c",
    baseURI: ABSOLUTE_URL,
    path: RELATIVE_URI,
    query: new Dictionary<string, string>() { { "FirstName", "Oktay" }, { "LastName", "Kır" } },
    headers: new Dictionary<string, string>() { { HEADER_API_KEY, HEADER_API_KEY_VALUE } } );
```

#### Create HttpPost request
```
var user = new User()
{
    id = "c833cbbf-7c81-4d30-b11a-88cf1c990b9c";
    FirstName = "Oktay"; 
    LastName="Kır";
}

Response<CreateUserResponse> response = JsonApiConsumer.Create<User, CreateUserResponse>(
    model: user,
    baseURI: ABSOLUTE_URL,
    path: RELATIVE_URI,
    headers: new Dictionary<string, string>() { { HEADER_API_KEY, HEADER_API_KEY_VALUE } } );
```

#### Post a file
```
Response<PostFileResponse> response = JsonApiConsumer.PostFile<PostFileResponse>(
    fileName: "filename",
    data: new byte[],
    baseURI: ABSOLUTE_URL,
    path: RELATIVE_URI,
    headers: new Dictionary<string, string>() { { HEADER_API_KEY, HEADER_API_KEY_VALUE } } );
```

#### Create HttpPut request
```
var user = new User()
{
    FirstName = "Oktay"; 
    LastName="Kır";
}

Response<UpdateUserResponse> response = JsonApiConsumer.Update<User, UpdateUserResponse>(
    id: "c833cbbf-7c81-4d30-b11a-88cf1c990b9c",
    model: user,
    baseURI: ABSOLUTE_URL,
    path: RELATIVE_URI,
    headers: new Dictionary<string, string>() { { HEADER_API_KEY, HEADER_API_KEY_VALUE } } );
```

#### Create HttpPatch request
```
var user = new User()
{
    FirstName = "CC"; 
}

Response<PatchUserResponse> response = JsonApiConsumer.Patch<User, PatchUserResponse>(
    id: "c833cbbf-7c81-4d30-b11a-88cf1c990b9c",
    model: user,
    baseURI: ABSOLUTE_URL,
    path: RELATIVE_URI,
    headers: new Dictionary<string, string>() { { HEADER_API_KEY, HEADER_API_KEY_VALUE } } );
```

#### Create HttpDelete request
```
Response<DeleteUserResponse> response = JsonApiConsumer.Delete<DeleteUserResponse>(
    id: "c833cbbf-7c81-4d30-b11a-88cf1c990b9c",
    baseURI: ABSOLUTE_URL,
    path: RELATIVE_URI,
    headers: new Dictionary<string, string>() { { HEADER_API_KEY, HEADER_API_KEY_VALUE } } );
```

### Contributing
1. Fork it ( https://github.com/OKTAYKIR/jsonapi-consumer/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request    
