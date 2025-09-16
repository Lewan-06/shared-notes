## Open Source Software (OSS)
### Misconceptions | <mark style="background: #009FFD;">multiple exam Q</mark>
- Lower cost: still require internal, external support and maintenance
- Security: malicious users could try create bugs in the code or exploiting of vulnerabilities
- Vender lock in: does not eliminate the dependency on specific technologies
- Better quality: may lack professional development resources or documentation 
### When to integrate open source into organisation | <mark style="background: #009FFD;">multiple exam Q</mark>
#### Product
##### Functionality
- Does software fulfil current and future needs?
- <mark style="background: #FF5582A6;">dealbreaker</mark> | <mark style="background: #D2B3FFA6;">indicator in-house investment</mark>
##### Licensing 
- Is license (legally) compatible with your business model?
##### Non-functional properties
- Will software work with existing systems?
- Can it handle expected workload? 
- <mark style="background: #FF5582A6;">dealbreaker</mark> | <mark style="background: #D2B3FFA6;">indicator in-house investment</mark>
##### Popularity and community 
- Positive metrics (GitHub stars, downloads)? 
- Active community to help?
- <mark style="background: #D2B3FFA6;">indicator in-house investment</mark>
##### Documentation 
- Technical documentation on installation, maintenance and troubleshooting? 
- User documentation: tutorials, reference manuals? 
- <mark style="background: #D2B3FFA6;">indicator in-house investment</mark>
##### Source code quality 
- Written in a language our team knows? 
- Code base well-structured, test and maintainable? 
- <mark style="background: #ABF7F7A6;">important for in-house development</mark>
##### Build 
- Well documented and reproducible (following process would lead to same result)?
- Able to build the code from start to finish? To work on it independently.
- <mark style="background: #ABF7F7A6;">important for in-house development</mark>
#### Development process
##### Project governance  
- Structure for decision making and leadership? 
- Roles and responsibilities well-defined?
- <mark style="background: #FF5582A6;">dealbreaker</mark>
##### Development workflow 
- Practice CI: unit testing, static analysis, test coverage analysis, spell-check documentation and dead links?
- <mark style="background: #ABF7F7A6;">important for in-house development</mark>
##### Code commits
- Regular commits by multiple contributors? 
- Clear descriptions and connected issues?
- Peer reviews/discussions? 
##### Project releases
- Frequent and up-to date? 
- History of maintenance and bug/security fixes? 
- LTS (long term support) branch: no new features, but only fixes for maximal stability? 
##### Support 
- Active channels such as forums, mailing lists or chats? Quick responses?
- Paid/professional support if necessary?
- <mark style="background: #D2B3FFA6;">indicator in-house investment</mark> | <mark style="background: #ABF7F7A6;">important for in-house development</mark>
##### Issue management 
- Dedicated platform for tracking issues and bugs? Quickly resolved? 
- Healthy ratio of open to closed issues? This shows whether issues are being addressed
- <mark style="background: #D2B3FFA6;">indicator in-house investment</mark> 
##### Contributions 
- Welcome/accept external contributions? Guidelines/review processes? 
- Evident of active engagement with contributors? 
- <mark style="background: #ABF7F7A6;">important for in-house development</mark>
### How to use open source? | <mark style="background: #FFA400;">an exam Q</mark>
#### Possible integrations
- Supported product
- Service
	- SaaS through cloud
	- Self hosted
- Dependent package
	- Smooth dependencies and updates
- Code installed/built from source
- Copied file/routine/class
	- Must be careful with licensing permissions
#### Supply chain risks
##### Endogenous
- Bugs
- Security vulnerabilities
##### Exogenous 
- Malicious contributors
- Geopolitical rifts: political tensions and international conflicts 
- Critical single points of failure: rely heavily on small number of maintainers
### Adapting OSS | <mark style="background: #A33B20;">no exam Q</mark>
#### Methods to adapt OSS to your system
- Configuration
- Contributed change
- Internal change
- Shim: small lightweight library (compatibility)
- Plugin: separate component that adds new features
- Fork: full copy of code base to develop independently
#### What to change
- Bugs
- Improvements
- Porting (run in different environment: add or create interfaces
- Refactoring: ensure unit tests are there, improvement, test, commit, repeat
### Contributing back
#### Why contribute? 
- Learn and professional advancement
- Give back to community
#### How to contribute? 
- Solve own problems
- Communicate with project team before making big changes
- Open issues and submit one clean commit per issue
- Separate style changes from functioanl changes
- Follow project guidelines, code style and communication methods
- Get contributions reviewed and be open to their feedback
- Be patient and persistent
- Add tests to measure performance
## Domain Driven Design (DDD)
### Effective modelling
#### Closely linking model with implementation | <mark style="background: #FFA400;">an exam Q</mark>
- Class and method names as well as test cases
#### Ubiquitous language
![[Screenshot 2025-05-30 144713.png]]
- Domain as backbone of language
- Entire must commit to using that language: diagrams, writing and speech
#### Developing knowledge ridge model | <mark style="background: #A33B20;">no exam Q</mark>
- Build models to capture essential knowledge of domain
- UML to visualize concepts, relationships and events
- Engage with domain experts and study domain literature 
##### Many to many relations | <mark style="background: #FFA400;">an exam Q</mark>
- Make relationship unidirectional
- Try to narrow relationship to make relationship many to one 
##### Entities vs value objects | <mark style="background: #009FFD;">multiple exam Q</mark>
- Persistent and change over time, because they have an identity and do not depend on attributes for identity vs cannot change aka immutable: if any field changes you have a new object
##### Services | <mark style="background: #A33B20;">no exam Q</mark>
1) Operations that do not fit an entity or object
2) Input/output other elements of domain model
3) No encapsulating state (output is directly determined by its inputs and no previous inputs)
##### Aggregates | <mark style="background: #009FFD;">multiple exam Q</mark>
- Cluster of associated objects treated as a unit, classes outside aggregate can only reference root
- Boundary: defines what's inside aggregate
- Root: single specific entity in aggregate that outside objects hold reference to
- Invariant: should hold in entire aggregate
	- Aggregates are created as a whole to enforce invariants
![[Screenshot 2025-05-30 154428.png]]
##### Factory | <mark style="background: #FFA400;">an exam Q</mark>
- Object or method dedicated to creating complex objects
- E.g: aggregates that must be created as a whole
##### Repository | <mark style="background: #FFA400;">an exam Q</mark>
- Objects of a certain type as conceptual set
- Adding/removing objects to such a repository triggers machinery behind to update database
##### Bounded context | <mark style="background: #009FFD;">multiple exam Q</mark>
- Boundary between particular domain models
- Why: manages complexity by separating domain into smaller parts
![[Pasted image 20250909225216.png]]
###### Relationships
- Shared kernel: some common concepts
- Customer/supplier: one depends on other
- Conformist: one follows changes by author
- Anti-corruption layer (ACL): interfaces to hide mess of other context 
#### Distilling model | <mark style="background: #A33B20;">no exam Q</mark>
- Less is more: prioritize domain concepts and avoid unnecessary complexity
##### Tactical 
- Develop model within single bounded context
##### Strategic
- Manage connections between bounded contexts
- Use of "context map" to highlight connections and translations
![[Pasted image 20250530161814.png]]
- Focus on distillation
#### Brainstorming and experimenting | <mark style="background: #FFA400;">an exam Q</mark>
- Collaborative techniques to identify meaningful domain events and boundaries
##### Event storming 
###### Chaotic exploration
![[Screenshot 2025-05-30 160920.png]]
###### Enforce the timeline
- Order the events as how the user would interact with our business in the real world
###### Identify swim lanes
- Parallelisation 
![[Screenshot 2025-05-30 161204.png]]
###### Identify pivotal events 
![[Screenshot 2025-05-30 161241.png]]
###### Identify candidates for bounded contexts 
![[Screenshot 2025-05-30 161440.png]]
###### What is core domain?
![[Screenshot 2025-05-30 161516.png]]