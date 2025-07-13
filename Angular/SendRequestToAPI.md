1. Import `HttpClient` service.
```
import { HttpClient } from '@angular/common/http';
```
2. Inject service using constructor
```
constructor(private httpClient:HttpClient) { }
```
3. Send request
```
this.httpClient.post<User>(this.url, JSON.stringify(user), {headers: {'content-type': "application/json"}})
```