# integration-bus-autogen
Integration Bus auto generator. Firstly to wrap store procedures and provide REST service.

# Way and details of future implementation.

* New DSL language written in Scala. 
* Most of the sourses is XML, and some ESQL files. 
* Every operator in DSL can be method in main gen-class
* Each operator can be build upon other operator that can see only it.
Let's say we writing *_response ESQL file in *_service project have first operator 'WRAP ESQL RESPONSE'.
Firstly, WRAP means that all operators in this line after WRAP will wrap by certain way a file with which we are working at the moment.
If next operator will be ESQL then we understand that we are working with *.esql file. 
The same conclusion with operator FLOW and files .flow / .subflow.
If we use ESQL RESPONSE then we generate .esql file for reponse flow.
Cases with WRAP, ESQL, RESPONSE.
- WRAP ESQL RESPONSE
- WRAP FLOW RESPONSE
- WRAP ESQL REQUEST
- WRAP FLOW REQUEST



