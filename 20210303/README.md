# REST API Unit Test

Service클래스에 통신API를 주입하는 방식으로 !
example)
```
final class RepositoryService {
    class func search(text: String, completion: @escaping (Result<RepositoryResult>) -> () ) {
        ...
        return AF.request ~~~어쩌고~
    }
}
```

이것을

```
protocol SessionProtocol {
    func request ...(기존에 alamofire에 있는 request함수)
}
```

```

final class RepositoryService {
    private let session: SessionProtocol
    
    init(session: SessionProtocol) {
        self.session = session
    }
    
    func search(text: String, completion: @escaping (Result<RepositoryResult>) -> () ) {
    
        ...
        return self.AF.request ~~~~~~
    }
}
```
이런식으로 바꾼다.




