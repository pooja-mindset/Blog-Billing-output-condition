# Blog-Billing-output-condition
Mindset Technical Blog- Maintaining Billing- output condition record with recipient email

Please find below the information on the code contents-

Include F01 have the local class with different methods to perform- create email object, create SAP office document, update Document with recipient email object, and create condition record with the created office document. These methods carry out the VV31 steps programmatically.
Report file contains the selection report, which inputs required fields (as shown below) and creates or updates the recipient email for the inputted customer and output type condition record, so this report can be directly used to test the methodology.

Two custom function modules are developed to utilize the standard subroutines in standard Include- FSSO5EC1 for SOMG operations. Function modules are developed because we cannot directly call the subroutines in object-oriented code i.e. class methods. Also if anyone is looking for the logic/ code reference to get the recipient email maintained for the customer (for which we use transaction- VV33 to view email), they can use the method- GET_CUSTOMER_RECIPIENT_EMAIL.

Also note that, while creating a condition record, we need to provide the condition table in the example I have taken the condition table is - 705. It depends on our system configuration.

In HANA system, VAKEY field is removed from the NACH table, so we have to get the condition record number first from the condition table and then use it to get the entry from NACH. Th code provided primarily is for ECC system, but also I have added commented code compatible for HANA system, so while utilizing on HANA system, we need to uncomment that code and comment those few lines valid for ECC. The guidelines are also provided what code to uncomment and what to comment in the code.
