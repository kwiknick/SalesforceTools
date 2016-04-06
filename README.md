# SalesforceTools
A place where helpful Salesforce Classes can be shared with anyone interested.

I wanted to share some of the generic classes that I've created in my time as a developer in Salesforce.  
Feel free to edit/improve anything that is a part of this repository.

The code included in this repository is licensed under GNU GPLv3 to encourage anyone that uses it to keep it open source.

# SendEmailWhenExceptionOccurs.apxc

I use this class in a try catch block to let me know when/if an exception occurs before a user can tell me.
An example would look like this:
```Apex
try {
	response = http.send(request);  
  if(!response.getStatus().equals(200)){
    SendEmailWhenExceptionOccurs sendExceptionEmail = new SendEmailWhenExceptionOccurs('Non 200 response recieved from REST call' + response.getBody());
  }
} catch (Exception e) {
	SendEmailWhenExceptionOccurs sendExceptionEmail = new SendEmailWhenExceptionOccurs(e);
}
```
