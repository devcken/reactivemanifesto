리액티브 선언문 (The Reactive Manifesto)
---------------------------------

각자의 도메인에서 움직이고 있는 조직들은 동일해보이는 소프트웨어를 만들기 위해 독립적으로 패턴을 찾아나서고 있습니다.
Organisations working in disparate domains are independently discovering patterns for building software that look the same.
이런 시스템들은 좀 더 탄탄하고, 좀 더 탄력있고, 좀 더 유연하며 현대의 요구 사항들을 받아들이는데 있어 더 나은 위치에 있습니다.
These systems are more robust, more resilient, more flexible and better positioned to meet modern demands. 

애플리케이션 요구사항들이 최근 몇년 동안 드라마틱하게 변화하고 있기에, 이러한 변화들이 일어나고 있습니다. 
These changes are happening because application requirements have changed dramatically in recent years.
불과 몇 년 전만해도 규모가 큰 애플리케이션은 10대의 서버, 수 초 내의 응답시간, 몇 시간 동안의 오프라인 유지보수 그리고 몇 기가바이트의 데이터를 가지고 있었습니다. 
Only a few years ago a large application had tens of servers, seconds of response time, hours of offline maintenance and gigabytes of data.
오늘날의 애플리케이션들은 모바일 디바이스부터 시작해 수천 개의 멀티 코어 프로세스에서 실행되는 클라우드 기반의 클러스터에 이르기까지 모든 곳에 디플로이되고 있습니다. 
Today applications are deployed on everything from mobile devices to cloud-based clusters running thousands of multi-core processors.
사용자들은 1000분의 1초의 응답 시간과 100% 업타임을 기대하고 있습니다.
Users expect millisecond response times and 100% uptime.
데이터는 페타바이트라는 단위로 측정되고 있죠.
Data is measured in Petabytes.
오늘날의 요구들은 단순히 예전 소프트웨어 아키텍쳐에 부합되지 않는다는 얘기입니다.
Today's demands are simply not met by yesterday’s software architectures.

우리는 시스템 아키텍쳐에 대한 논리 정연한 접근방법이 필요하다고 믿으며, 필요로 하는 모든 부분들이 이미 개별적으로 들어나 있다고 믿습니다: 우리는 즉각 반응할 수 있고, 회복 가능하고, 탄력적이며, 메시지가 주도하는 시스템을 원합니다. 우리는 이런 시스템들을 리액티브 시스템이라고 부릅니다.
We believe that a coherent approach to systems architecture is needed, and we believe that all necessary aspects are already recognised individually: we want systems that are Responsive, Resilient, Elastic and Message Driven. We call these Reactive Systems.

리액티브 시스템으로써 만들어지는 시스템들은 좀 더 유연하고, 느슨하게 연결되어 있으며 [확장 가능](/glossary#Scalability)합니다. 
Systems built as Reactive Systems are more flexible, loosely-coupled and [scalable](/glossary#Scalability).
이런 특성들은 시스템들을 개발하기 쉽고 변화를 잘 받아들이도록 만들어줍니다.
This makes them easier to develop and amenable to change.
그러한 점들이 [장애](/glossary#Failure)가 일어나지 않도록 더욱 더 잘 견디도록 해주며 장애가 일어났을 때 재앙보다는 간결하면서도 우아하게 그것들을 처리할 수 있도록 해줍니다. 
They are significantly more tolerant of [failure](/glossary#Failure) and when failure does occur they meet it with elegance rather than disaster.
리액티브 시스템들은 [사용자](/glossary#User)에게 효과적인 상호작용 피드백을 줄만큼 상당히 응답적입니다.
Reactive Systems are highly responsive, giving [users](/glossary#User) effective interactive feedback. 

*리액티브 시스템들은:*
*Reactive Systems are:*

* <a name="Responsive"></a>**즉시 반응하는**: [시스템](/glossary#System)은 가능한 모든 상황에서 적시에 응답합니다.
responds in a timely manner if at all possible.
즉시 응답성은 사용성과 활용성의 주춧돌이지만, 그 이상으로, 문제를 빠르게 감지하며 효과적으로 다룬다는 것을 의미합니다.
Responsiveness is the cornerstone of usability and utility, but more than that, responsiveness means that problems may be detected quickly and dealt with effectively.
즉시 응답하는 시스템들은 아주 빠르고 일관된 응답 시간 제공과 신뢰도 있는 상한선 수립에 집중함으로써 서비스에 대한 동일한 품질을 제공하게 됩니다.
Responsive systems focus on providing rapid and consistent response times, establishing reliable upper bounds so they deliver a consistent quality of service.
이런 일관성 있는 동작들은 차례 차례, 오류 핸들링을 간소하고 최종 사용자의 자신감을 만들어 주며 좀 더 많은 상호작용을 일으켜줍니다.
This consistent behaviour in turn simplifies error handling, builds end user confidence, and encourages further interaction.
* <a name="Resilient"></a>**회복 가능한**: 시스템은 [장애](/glossary#Failure)에도 불구하고 응답성을 유지할 수 있습니다. 
The system stays responsive in the face of [failure](/glossary#Failure).
이러한 점은 고가용성의, 임무에 있어 필수적인 시스템들에만 적용되는 것은 아닙니다 - 회복력이 없는 시스템들은 장애 이후에 응답하지 못할 겁니다. 
This applies not only to highly-available, mission critical systems — any system that is not resilient will be unresponsive after a failure.
회복력은 [복제](/glossary#Replication), 억제, [격리](/glossary#Isolation) 그리고 [위임](/glossary#Delegation)에 의해 달성할 수 있습니다. 
Resilience is achieved by [replication](/glossary#Replication), containment, [isolation](/glossary#Isolation) and [delegation](/glossary#Delegation).
컴포넌트들이 다른 컴포넌트들과 격리되고, 그 덕분에 장애 발생 후에 전체 시스템을 위태롭게 만들지 않고 회복할 수 있는 시스템의 각 부분들을 보장하는 각각의 컴포넌트 사이에 장애가 내재되게 됩니다.   
Failures are contained within each [component](/glossary#Component), isolating components from each other and thereby ensuring that parts of the system can fail and recover without compromising the system as a whole.
각 컴포넌트의 회복은 다른 (외부의) 컴포넌트에 위임되며 고가용성은 필요한 곳에서 복제에 의해 보장됩니다.
Recovery of each component is delegated to another (external) component and high-availability is ensured by replication where necessary.
컴포넌트의 클라이언트는 컴포넌트의 장애를 다루는 짐을 지지 않습니다.
The client of a component is not burdened with handling its failures.
* <a name="Elastic"></a>**유연한**: 시스템은 처리량이 다른 상황에서도 응답성을 유지합니다.
The system stays responsive under varying workload.
리액티브 시스템들은 입력을 서비스하기 위해 할당된 [리소스](/glossary#Resource)들이 늘어나거나 줄어드는 입력율의 변화에 반응할 수 있습니다.
Reactive Systems can react to changes in the input rate by increasing or decreasing the [resources](/glossary#Resource) allocated to service these inputs.
이것은 논쟁이 되는 요점 혹은 주요한 병목 원인이 없는 설계를 넌지시 나타냅니다. 이런 설계는 컴포넌트를 샤드 혹은 복제하고 그런 컴포넌트들로 입력들을 분배하기 위한 능력의 원인이 됩니다.
This implies designs that have no contention points or central bottlenecks, resulting in the ability to shard or replicate components and distribute inputs among them.
리액티브 시스템들은 적절한 라이브 성능 측정을 제공함으로써 반응하는만큼, 예측 가능한 스케일링 알고리즘을 제공합니다.
Reactive Systems support predictive, as well as Reactive, scaling algorithms by providing relevant live performance measures.
그런 알고리즘들은 범용 하드웨어와 소프트웨어 플랫폼 상에서 가성비가 좋은 방법으로 [유연성](/glossary#Elasticity)을 달성합니다.
They achieve [elasticity](/glossary#Elasticity) in a cost-effective way on commodity hardware and software platforms.
* <a name="Message-Driven"></a>**메시지 주도**: 리액티브 시스템들은 느슨한 연결, 격리 그리고 [위치 투명성](/glossary#Location-Transparency)을 보장하는 컴포넌트들 사이의 경계를 만들어내기 위해 [비동기적인](/glossary#Asynchronous) [메시지 전달](/glossary#Message-Driven)에 의존합니다.
Reactive Systems rely on [asynchronous](/glossary#Asynchronous) [message-passing](/glossary#Message-Driven) to establish a boundary between components that ensures loose coupling, isolation, and [location transparency](/glossary#Location-Transparency).
이 경계라는 것은 메시지로 [장애](/glossary#Failure)를 위임하기 위한 수단들을 제공하기도 합니다.
This boundary also provides the means to delegate [failures](/glossary#Failure) as messages.
명시적인 메시지 전달의 도입은 시스템 내 메시지 큐를 형성하고 모니터링하며 필요할 때 [배압](/glossary#Back-Pressure)을 제공하여 로드 관리, 유연성 그리고 흐름 제어를 활성화합니다.
Employing explicit message-passing enables load management, elasticity, and flow control by shaping and monitoring the message queues in the system and applying [back-pressure](/glossary#Back-Pressure) when necessary.
커뮤니케이션의 한 수단인 위치 투명성 메시징은 클러스터에 걸쳐 동일한 구조와 의미로 동작하거나 동일한 호스트 사이에서 동작하도록 장애 관리가 가능하도록 해줍니다.  
Location transparent messaging as a means of communication makes it possible for the management of failure to work with the same constructs and semantics across a cluster or within a single host.
[넌블로킹](/glossary#Non-Blocking) 커뮤니케이션은 더 적은 시스템 오버헤드를 이끌도록, 동작하는 동안 [리소스](/glossary#Resource)를 소비만 하는 수신자들을 허용합니다. 
[Non-blocking](/glossary#Non-Blocking) communication allows recipients to only consume [resources](/glossary#Resource) while active, leading to less system overhead.

규모가 큰 시스템들은 다른 더 작은 시스템들로 구성되며, 그러므로 시스템 구성 요소의 리액티브 프로퍼티에 의존적입니다.
Large systems are composed of smaller ones and therefore depend on the Reactive properties of their constituents.
이것이 의미하는 바는 리액티브 시스템들이 설계 원칙을 적용하여 이런 프로퍼티들을 구성 가능하도록 그것들이 유연성의 모든 단계에 적용된다는 것입니다.
This means that Reactive Systems apply design principles so these properties apply at all levels of scale, making them composable.
세상에서 가장 큰 시스템들은 이 프로퍼티들에 기반하는 아키텍쳐에 의존하며 날마다 수억명의 사람들이 필요로 하는 바를 서비스합니다. 
The largest systems in the world rely upon architectures based on these properties and serve the needs of billions of people daily.
매번 그런 프로퍼티들을 재발견하지 말고 처음부터 의식적으로 앞서 말한 설계 원칙들을 제공해야 할 시간입니다.
It is time to apply these design principles consciously from the start instead of rediscovering them each time.

[선언문에 서약하세요](http://www.reactivemanifesto.org/#sign-button)
