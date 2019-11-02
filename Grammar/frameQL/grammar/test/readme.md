# Test program for combining frontend (VQL) and backend(Eva) query optimizer
The query optimizer of EVA, which is being developed by another team, is an optimizer that takes in a query and find equivalent queries that could be evaluated faster. We build a test program in evalQuery.py that takes in a text file of query and return two lists that could be recognized by EVA query optimizer 
## Generate inputs for query optimizer
Transform the sql statement in test.txt to a list of parsed predicates and a list of opertors  
```
python3 evalQuery.py test.txt
```

We used a design patterns called listener that will trigger actions when "walk" the grammar parse tree.
The listener is generated by ANTLR and we made relavent changes between line *4450* to line *4500* in **frameQLParserLinstener**.

## Furture work
We are working with the EVA engine group and is on our way to integrate our code with their video processing backend.
The goal is to have a single product that takes in a query and return query result generated from the EVA engine.
We want to 

Call query optimizer in test.txt with the generated lists;  

Deal with expressions on both sides of the logicalOperator are in parentheses. 