## Knowledge Graph

The knowledge graph of OSNs ₲ is a tuple ₲ = (U, E, T) where 

- U represents a group of users
- E ⊆ U × U represents a group of edges between users
	- Represents that there is a trust relationship between users. 
	- Edge in knowledge graph are represented as triples(h,r,t), head has a relation with tail. 
- The value of trust relationship we call trust value, denoted as t(𝑣, 𝑒,𝑢), is direct, because of v and u are connected directly by the edge e. 
- A is connected to B directly with a trust value 0.76, which can be denoted as (A, 0.76, B).

## Embedding Models for Link Prediction

### Translation-Distance-Based Models

Which usually use distance-based functions to define the scoring function for link prediction. After the relation is translated, the distance is used to measure the credibility between two entities.

#### TransE 
One of the earliest models for link prediction, which uses the relation for translating the head entity to a tail entity.  TransE is a well-known, early and simple model that regards a relation as a translation from a head entity to a tail entity. It uses a distance scoring function as follows:
``f ( h, t ) = sqrt({|| h + r − t ||})``

It has difficulty dealing with multirelational graphs; it is limited by its simple translation operation as well as its lack of a discrimination policy for all kinds of relations. 

#### TransH 
TransH introduces a hyperplane, and TransR uses a relation-specific space to handle different relations, excavating more semantic information. 

#### TransHR 
Model focuses on the embedding of hyperrelational data. These models are similar in nature; the only improvement is in translating the head entities to tail entities.

#### TransMS 
Regards the head entity, relation and tail entity as a subject, predicate and object, respectively, as in a sentence. In this way, it considers the semantics between the head entity and the relation as well as the semantics between the relation and the tail entity, which is not done in previous models. It uses the nonlinear function p ( e, r ) (this is the tanh function) instead of a linear function to translate the semantics, that is, to translate both h and r to t, obtaining the final tail-entity embedding vector as 

``t ⊥ = P ( p ( h, r ) , t )``
and obtaining the head-entity embedding vector from the converse semantic transfer

``h ⊥ = P ( p (− t, r ) , h )``
