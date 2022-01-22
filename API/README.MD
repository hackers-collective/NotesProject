# Application Programming Interface

A way for two different pieces of code or human and some code to interface with each other.

API is everywhere, From Web to Computer's Driver(s) has API(s).

## Types of API calls

- Some calls to APIs can change things on the server, others return data without changing anything.

- Safe Request - one that does not change anything on the server. It is safe because of just asking what's going on the server, not asking to do some activity on the server.

- Not a Safe Request - the server has changed just by changing something over a call and making server state changed.

- Idempotent call - When we change X with A in the server on a call, and again we do the same changing X with A in the server, but nothing is changed as it is the same happened. API calls that return the same result no matter how many times you call them are known as idempotent. Since, it only changes things the first time you execute it and does not make any changes on subsequent calls.

