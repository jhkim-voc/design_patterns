# Understand UML class diagram and timing diagram

 I will not mention all the elements of UML here, I just want to talk about the relationship between the classes in the class diagram.  
It is enough to understand what the lines and arrows in the class diagram mean. Cope with daily work and communication.  
At the same time, we should be able to match the meaning expressed by the class diagram with the final code.
With this knowledge, there is no problem looking at the design pattern structure diagram in the following chapter.

 All the graphics in this chapter are drawn using Enterprise Architect 9.2. For all the examples, see design_patterns.EAP in the root directory.

# Start with an example

 Please see the following class diagram, the relationship between classes is what we need to pay attention to:

![uml_class_struct](./_static/uml_class_struct.jpg)

- The class diagram structure of the car is << abstract >>, indicating that the car is an abstract class.
- It has two inherited classes: car and bicycle. The relationship between them is to realize the relationship, which is indicated by a dotted line with a hollow arrow.
- The relationship between the car and the SUV is also an inheritance relationship. The relationship between them is a generalized relationship, which is indicated by a solid line with a hollow arrow.
- The relationship between the car and the engine is a combination, which is indicated by a solid line with a solid arrow.
- There is an aggregation relationship between students and classes, which is indicated by a solid line with a hollow arrow
- The relationship between the student and the ID card is shown by a solid line.
- Students need to use bicycles to go to school, which is a dependent relationship with bicycles, which are indicated by dotted lines with arrows.

Below we will introduce these six relationships.

---
# Relationship between classes

## Generalization

 The inheritance structure of the class is expressed in UML as: generalize and realize.

 The inheritance relationship is the relationship of is-a. If between two objects can be expressed by is-a, it is the relationship of inheritance. (..is ..)
e.g.) Bicycles are cars, cats are animals

 The generalization relationship is directly represented by a hollow arrow, as shown in the following figure. (A inherits from B)

![uml_generalization](./_static/uml_generalization.jpg)

e.g.) The car is realized in reality, and the car can be used to define specific objects; the general relationship between the car and the SUV.

![uml_generalize](./_static/uml_generalize.jpg)

Note: In the final code, the generalization relationship is expressed as inheriting non-abstract classes.

## Realize

 The realization relationship is indicated by a dotted line with a hollow arrow.

e.g.) "Car" is an abstract concept and cannot be used directly to define objects in reality; only specific subclasses (car or bicycle) can be used to define objects.
(The "car" class is represented by an abstract class in C ++ and there is the concept of interface in JAVA, which is easier to understand.)

![uml_realize](./_static/uml_realize.jpg)

Note: In the final code, the realization relationship is expressed as inherited abstract class.

## Aggregation

 The aggregation relationship is represented by a straight line with a hollow diamond arrow, as shown in the following figure, A is aggregated to B, or B is composed of A.

![uml_aggregation](./_static/uml_aggregation.jpg)

 Aggregation relationship is used to represent the relationship between entity objects, which means that the whole is composed of part of the semantics.
For example, a department is composed of multiple employees.

 Unlike the combination relationship, the whole and part are not strongly dependent, even if the whole does not exist, the part still exists.
For example, if the department is revoked, the personnel will not disappear, they still exist.

## Composition

 The combination relationship is represented by a straight line with a solid diamond arrow, as shown in the following figure, A is composed of B, or B is composed of A.

![uml_composition](./_static/uml_composition.jpg)

 As with the aggregation relationship the combination relationship also represents the semantics of the overall composition of parts.
For example, the company is composed of multiple departments.

 However, the combination relationship is a special aggregation relationship with strong dependence. If the whole does not exist, the part will not exist.
For example, if the company does not exist, the department will also not exist.

## Association

 The association relationship is represented by a straight line. It describes the structural relationship between objects of different classes.
It is a static relationship usually irrelevant to the running state, generally determined by factors such as common sense.
It is generally used to define between objects Static, natural structure. Therefore, the association relationship is a "strong association" relationship.

 For example, there is an association between passengers and tickets; students and schools are an association.

 The association relationship does not emphasize the direction by default, indicating that the objects know each other.
If the direction is particularly emphasized, as shown in the following figure, it means that A knows B, but B does not know A.

![uml_association](./_static/uml_association.jpg)

Note: In the final code, the associated objects are usually implemented in the form of member variables.

## Dependency

 Dependencies are represented by a set of dotted lines with arrows. The following figure shows that A depends on B.

 Obviously, dependence also has a direction. Bidirectional dependence is a very bad structure. We should always maintain unidirectional dependence to prevent the generation of bidirectional dependence.

Note: In the final code, the dependency relationship is reflected in the class constructor and the incoming parameters of the class method, and the arrow points to the call relationship.
The dependency relationship "uses" the other party's methods and properties in addition to temporarily knowing the other party.

## Timing diagram

 In order to show the details of the interaction between objects, the subsequent chapters on the analysis of design patterns will use timing diagrams.

 Sequence diagram is a diagram showing the interaction between objects, these objects are arranged in chronological order.
The sequence diagram shows the objects involved in the interaction and the sequence of message interaction between the objects.

 The modeling elements included in the sequence diagram are: objects(Actor), lifeline, focus of control, message and so on.

 Regarding the timing diagram the following article will introduce the concept in more detail.
For more example applications, see the timing diagram in the mode of the subsequent chapter.
