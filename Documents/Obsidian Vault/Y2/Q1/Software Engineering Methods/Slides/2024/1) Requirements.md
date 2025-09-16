## Engineering Design Process aka Engineering Method 
- Steps to create function products and processes
- Iterative
- Decision making process to achieve objective with given resources
### Software Development Lifecycle | <mark style="background: #A33B20;">no exam Q</mark>
![[Screenshot 2025-05-19 195229.png]]
#### Requirements engineering 
- Part of the "analysis" ^^
- Requirement: feature or constraint of the system 
- Expressed in natural language or model based
	- Examples of models
		- Graphs such as UML diagrams and examples of UML are below
			![[Screenshot 2025-05-19 195719.png]]
			- Used for communication between developers as well as with stakeholders
			- Use case diagram
			![[Screenshot 2025-05-19 195915.png]]
			- Sequence diagram
		- Formulas
			- Useful for highly precise and complicated systems. E.g: to check if security requirements were fulfilled
		- Pseudo code
			- When having implement existing algorithms or prototypes
##### How not to miss stakeholders? | <mark style="background: #A33B20;">no exam Q</mark>
- Customers, end users, managers, sponsors, developers, IT support, marketing
- Think about edge cases. E.g: minorities or disabled people
- Future groups
- IT department is also a party to be considered 

| Elicitation techniques                                                                                                                                           | Pros \| <mark style="background: #A33B20;">no exam Q</mark>               | Cons \| <mark style="background: #A33B20;">no exam Q</mark>                                                                                                                |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Interviews with stakeholders                                                                                                                                     | 1) People love talking (about their work), so could give a lot of insight | 1) Could be difficult to bridge the gap between domain knowledge and technical knowledge                                                                                   |
| Questionnaires                                                                                                                                                   | 1) General opinions. 2) Edge case                                         | 1) Requires prior domain knowledge to make such a questionnaire. 2) Respondents might want to give socially conform answers or questions might lean into a specific answer |
| Writing scenarios/use cases with stakeholders: start state, events, potential errors + handling, parallel activities and finish                                  | Stakeholders can easily relate scenario's to real life exam               | not in slides                                                                                                                                                              |
| Contextual inquiry: observe people while they work                                                                                                               | not in slides                                                             | not in slides                                                                                                                                                              |
| Brainstorming                                                                                                                                                    | not in slides                                                             | not in slides                                                                                                                                                              |
| Use case diagrams 1) Simple version is easy to communicate functionalities with stakeholder. 2) Complex version can be used for communication between developers |                                                                           |                                                                                                                                                                            |

##### User vs system requirement | <mark style="background: #009FFD;">multiple exam Q</mark>
- Service to provide to users vs detailed description of operation constrains
#####  Requirement verifiability 
- Imprecise: "easy to use" and "errors should be minimized"
- Verifiable: measurable: time and amounts
##### SMART | <mark style="background: #FFA400;">an exam Q</mark>
- Specific, measurable, achievable, relevant, time related
##### Contract binding | <mark style="background: #A33B20;">no exam Q</mark>
- Companies propose solution based on list of user reqs, once company is chosen, system req is made
##### Functionality vs non-functional  | <mark style="background: #009FFD;">multiple exam Q</mark>
- Service to provide vs constraints
##### Requirement analysis process 
![[Screenshot 2025-05-20 185315.png]]

| Prioritisation techniques | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Advantages \| <mark style="background: #A33B20;">no exam Q</mark>                                                                                   | Disadvantages \| <mark style="background: #A33B20;">no exam Q</mark>                                                                                                            |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Moscow method             | Requirement categories: must have, should have, could have and won't have. Recommended to describe each requirement with the corresponding category.                                                                                                                                                                                                                                                                                                                                                                                                             | 1) Simple. <br>2) Helps to manage scope. <br>3) Easy to argue with stakeholders                                                                     | 1) Difficult to rank requirements within category. <br>2) Ambiguity "won't have" about excluding project vs next release. <br>3) Subjective might skew priority to new features |
| Kano                      | Requirement categories: <br>1) Basic: missing leads to dissatisfied customers, but no increase in customer satisfaction). <br>2)  performance needs (directly impact customer satisfaction). <br>3) excitement needs (delight of customers if present, otherwise no customer dissatisfaction if not present). <br>4) Indifferent needs (no difference customer satisfaction) and <br>5) reverse needs (customer dissatisfaction if implemented) Steps: 1) Identify features. 2) Survey customers. 3) Analyse data. 4) Prioritize feature 5) Implement and review | 1) Aligns with customer needs and expectations. <br>2) Focus on customer satisfaction and loyalty. <br>3) Insights into what features are essential | 1) Require customer surveys + analyses to categories features. <br>2) Revaluation if customer expectations change                                                               |
##### UML | <mark style="background: #009FFD;">multiple exam Q</mark>
#UML 
##### Requirement to issues | <mark style="background: #A33B20;">no exam Q</mark>
- Challenge: requirements often too broad for a single issue
- Approach: break down into subtasks
