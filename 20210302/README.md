# MVVM 스터디

1. mvvm에서 query를 할 때에는 service layer를 두자. viewModel에서 직접 쿼리하지말고 해당 service layer를 가지고 쿼리를 한다.
[example](https://gist.github.com/eunjin3786/14fba92d5f65847e956bcb8a30139012#file-afterservicelayer-swift)

-> todo) 인터넷에서 MVVM에 대해서 검색하게되면 Model에 비지니스로직이 들어가 있는데.. 다른 방법이 있는걸까 확인

2. viewModel에서 subscribe는 쓰지말자 

-> 유지보수가 매우 힘들다. 아예 viewModel에서 disposeBag을 지워버리자. concat이나 다른 오퍼레이터들을 이용해야 하는듯싶다.

-> subscribe를 함으로인해 weak로 블록을 가져가게 되면 disposebag을 넣기가 애매해지는 상황도 자동적으로 해결됨.


