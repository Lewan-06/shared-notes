## Problem statement
A system to answer questions for students for a particular course so they are answered in a fair, consistent order. The order should be first come, first serve. This means that the student that made the first request (longest ago) should be the next to get a TA assigned to it.
## MOSCOW
### Must have
- System can handle a load of 600 students per lab with multiple labs at the same time.
- Questions that can be answered by a particular TA, are forwarded to the next TA.
- Students can ask questions before, during but not after a lab session has ended.
- TA should be able to decline a request. For example, when a student is not present in the lab.
### Should have 
- TAs can also have the role of student to ask questions for courses for which they are not a TA.
- Head TAs or the teacher of a course can configure how many  questions can make at a particular moment in time for a particular lab.
- Students can give feedback to a TA bound to a particular request.
- Head TAs or the teacher of a course can configure to have slotted time slots for asking questions.
- User accounts and passwords are bound to the central TU Delft database. This way, we are sure people outside the TU can not create requests for particular labs.
### Could have 
- TAs can view the history of requests per student per lab.
- The teacher of a course should be able to see statistics on how well a particular TA performs, like how many requests they resolved, declined, forwarded per lab session.
- Students can see the staff/TA that work for that course.
- The user interface has a dark theme and light theme.
- Students are able to see how many people are in front of them in the queue.
- Head TAs and teachers can make announcements for a lab session.
- TAs can filter the requests/questions based on a particular topic/assignment the question is related to.
### Won't have
- TAs can view the grades from students.
- Chat between students and TAs.
## Reflection
### (a) Did you have sufficient details to compose your requirements? 
\> Yes, in order to make sure of this all three of us (our group had 3 people), made notes of the questions we asked individually. Then we formulated the requirements independently and discussed. This way, we were able to discuss different requirements and rankings within MOSCOW.
### What did you(r  group) do that allowed this to happen / what could you do differently to get  sufficient requirements?
\> Beforehand, we decided on the structure of the conversation with the TA. With a bit more time, we could have also prepared questions. 
### (b) Explain whether you think an interview is the best way to figure out the problem and the details of the requirements.
\> People (stakeholders) love talking about their work, so little effort from our (engineer's) side is required to extract requirements. However, it can be difficult to bridge the gap between domain knowledge and technical knowledge. With this we mean knowledge the stakeholder has about their work could be difficult to explain to engineers. Additionally, we noticed, that technical details like discussing the TU Delft sso (single-sign-on) can be difficult.
### (c) Suggest a different interaction that you think may be useful for defining the problem statement and requirements, either as replacement of an interview or as addition to an interview. Explain why in a few sentences.
\> Other requirement elicitation techniques are: questionnaires, writing scenarios/use cases with stakeholders, context inquiry, brainstorming and use case diagrams. Here, questionnaires are a kind of passive way of extracting requirements. It does require prior domain knowledge however, and is less likely to receive a lot of responses. These questionnaires can be done next a stakeholder interview. For instance, before to prepare the interview and clear up details or afterwards if after the interview requirements were still too ambiguous.