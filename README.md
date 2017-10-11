# integration-bus-autogen
Integration Bus auto generator. Firstly to wrap store procedures and provide REST service.

# Way and details of future implementation.
## DSL
* New DSL language written in Groovy. 
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
- There must be variables that will be mapped from req to resp. So, It's probably will be a good idea to provide keyword word MAP. And source of variable in request and destination of variable in response(+vise versa) will be placed under variable-kayword. For instanse: MAP CORELID. MAP means assing from req to resp(and vie versa) and CORELID means name of the variable and source+destination. 
## Basic I/O
As template engine I decided to use Thymeleaf. It natively working with XML, and also working with plain .txt files. 
To generate ESQL files I can change file extension in runtime. The dame situation with rest descriptor that doesn't have explicit extention.
