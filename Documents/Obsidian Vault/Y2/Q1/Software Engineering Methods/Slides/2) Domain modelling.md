 Part of "design" in #Software_development_lifecycle 
## Software design
- Goal: transform requirement into implementation
### Bad design
- Spaghetti code: linear dependencies
- Non-scalable
- Difficult to split across team
- Non-testable
- Non-reusable
## Domain driven design
#### Ubiquitous language
![[Screenshot 2025-05-30 144713.png]]
- Domain as backbone of language
- Entire team must commit to using that language: diagrams, writing and speech
### Bounded context | <mark style="background: #009FFD;">multiple exam Q</mark>
- Boundary between particular domain models
- Why: manages complexity by separating domain into smaller parts
- Per pivotal event, swimlane or actor 
![[Pasted image 20250909225216.png]]
#### Relationships
- Shared kernel: some common concepts
- Customer/supplier: one depends on other
- Conformist: one follows changes by author
- Anti-corruption layer (ACL): interfaces to hide mess of other context 
### Context maps
#### Relationships
##### Upstream/downstream
- Downstream influenced by upstream
##### Types
###### Partnership
- Dependent goals
###### Conformism
- Upstream has rules for downstream to follow (E.g: security guidelines)
###### Anti-Corruption Layer
- Upstream has rules, but adapter makes this translation (downstream is more independent than conformism)
###### Shared-kernel
- Common codebase
###### Customer-supplier
- Developer team of upstream must take into account downstream
###### Open-host service
- Anybody can integrate to system
###### Published language
- Downstream input and output of context follows documented language of upstream
###### Separate ways
- Start together, evolved away from each other
### Event storming 
#### Chaotic exploration
![[Screenshot 2025-05-30 160920.png]]
#### Make a timeline
- Order the events as how the user would interact with our business in the real world
#### Identify swim lanes
- Parallelisation 
![[Screenshot 2025-05-30 161204.png]]
#### Identify pivotal events 
![[Screenshot 2025-05-30 161241.png]]
#### Identify candidates for bounded contexts 
![[Screenshot 2025-05-30 161440.png]]
#### What is core domain?
![[Screenshot 2025-05-30 161516.png]]
