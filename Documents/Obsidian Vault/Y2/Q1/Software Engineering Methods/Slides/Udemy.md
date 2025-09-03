## Agile vs waterfall
### Waterfall
- Clear requirements and fixed scope
### Agile
- Requirements are unstable and may change frequently
	- Can be updated during sprints
#### Example software's
- Scrum
- Kanban
## Spaghetti code
- Drawbacks
	- Unstructured
	- Hard to understand
	- Difficult to maintain
- Often seen with sequential code
### Solutions
#### Structured programming
- Data structures, subroutines
#### Object oriented
- Each object acts as separate object
- Objects interact/refer with each other
##### Process
###### Collect requirements
- Functional/non-function: features vs performance/legal/documentation
- Specific: the app must do ...
###### Use cases (waterfall)
- Title (short), actor (user) and scenario (multiple sentences on how system works in this case)
###### User story (agile)
- As a \<type_user>, I want to \<some_goal> so that \<some_reason>
	- Smaller than use cases
- Goal is to start discussions instead of covering details
###### Epic
- Grouped user stories (functionally related often)
##### Object
- Properties
- Identity: changing state of one object, does not change any other
- Behaviour: performs action
##### Class
- Blueprint of an object: what an object will be
	- Properties
	- Actions: methods
##### Abstractions
- Describing complex problems by ignoring irrelevant details
##### Encapsulation
- Packing together objects and methods in a class, we do not want to show the internal implementations
	- Protecting classes dependencies as much as possible
##### Inheritance
- Reusing existing class implementation
###### Polymorphism
- Working with classes without knowing their exact type
- Method overriding: different implementation than the parent class

#### UML (Uniform modelling language)
- Graphical notation to model systems
- Not fixed to any programming language
- Communication tool for developers (instead of inspecting source code)
##### Use case diagram
- Functionality of a system from a user pov
- Not replacement for use case descriptions, they are more descriptive
![[Screenshot 2025-05-23 143534.png]]
###### <\<include>> vs <\<extend>>
- Include: one use case requires behaviour of another
- Extend: optional and adds behaviour to another use case
##### Class diagram (type structural)
- Objects, attributes operations and relations
![[Screenshot 2025-05-24 133453.png]]![[Screenshot 2025-05-24 133516.png]]
- Generalisation: inheritance between classes (also can be part of use case diagrams to show a child gets all functions from its parent)
![[Screenshot 2025-05-24 133528.png]]
- Realisation: implements behaviour from an interface
![[Screenshot 2025-05-24 133550.png]]![[Screenshot 2025-05-24 133611.png]]
##### Sequence diagram (type behavioural)
- What happens and interactions between options
![[Screenshot 2025-06-02 201740.png]]
- Horizontal arrows represent the method calls
- Box represents an object, represented as "\<alias> : \<type>"
![[Screenshot 2025-06-02 201830.png]]
async: non-striped sync message
#####  Activity diagram
![[Screenshot 2025-06-02 201857.png]]
![[Screenshot 2025-06-02 201925.png]]
##### State diagram
- Initial node ^ is start,
- Each rounded box is a state
- Arrow is a transition between states
- Each arrow can have \[] to containing the mandatory conditions for that state