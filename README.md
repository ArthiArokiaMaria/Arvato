# Arvato
## Prerequisite:  Sample API Key: Dpma1c4vi7EQkVBc0ZLObWf9wIHpK5lm You can also generate your own API key by following 
steps: 1. Go to https://apilayer.com/signup or https://fixer.io/login 
2. Sign up and go to Free subscription 
3. Generate the API Key

## Scenario 1 : To verify 1000 NOK is converted to INR 
Given  Iniliazie API service  
And add the parameters “from currency” , “ to currency” and “amount” 
Then add the generated api key  
When Api is invoked for the given data  
Then Verify and validate the response after conversion is valid  
input data : 
amount |  FromCurrency |  ToCurrency 
1000       | USD | INR 
200    | NOK | INR   
https://api.apilayer.com/fixer/convert?from=NOK&amp;to=INR&amp;amount=1000&amp;apikey=Dpma1c4vi7EQkVBc0ZLObWf9wIHpK5lm 
Response : {     "success": true,     "query": {         "from": "NOK",         "to": "INR",         "amount": 1000     },     "info": {         "timestamp": 1661515744,         "rate": 8.254661     },     "date": "2022-08-26",     "result": 8254.661 } 
Test case status :  pass      

## Scenario 2  : Try to convert floating numbers from NOK to INR
Given  Iniliazie API service  
And add the parameters “from currency” , “ to currency” and “amount” 
Then add the generated api key  
When Api is invoked for the given data  
Then Verify and validate the response after conversion is valid  
Input Data :  
amount |  FromCurrency |  ToCurrency 
10.20       | USD | INR
200.50   | NOK | INR 
https://api.apilayer.com/fixer/convert?from=NOK&amp;to=INR&amp;amount=10.20&amp;apikey=Dpma1c4vi7EQkVBc0ZLObWf9wIHpK5lm {     "success": true,     "query": {         "from": "NOK",         "to": "INR",         "amount": 10.2     },     "info": {         "timestamp": 1661520064,         "rate": 8.28228     },     "date": "2022-08-26",     "result": 84.479256 }  
Test case status :  pass  
## Scenario 3 : Try to convert integer separated with commas from NOK to INR 
Given  Iniliazie API service  
And add the parameters “from currency” , “ to currency” and “amount” 
Then add the generated api key 
When Api is invoked for the given data 
Then Verify and validate the response after conversion is valid 
Input Data :  
amount |  FromCurrency |  ToCurrency 
10,000,2020       | USD | INR 
200,500   | NOK | INR 
https://api.apilayer.com/fixer/convert?from=NOK&amp;to=INR&amp;amount=200,500&amp;apikey=Dpma1c4vi7EQkVBc0ZLObWf9wIHpK5lm
{     "success": false,     "error": {         "code": 403,         "type": "invalid_conversion_amount",         "info": "You have not specified an amount to be converted. [Example: amount=5]"     } }  
Test case status :  Fail 
# Explanation : I have assumed the test case has been fail because in some cases the amount might have been separated by commas . It’s not specified anywhere in the API specification .  I marked is as failed based on my assumption .  

## Scenario 4 : Try to convert integer INR to NOK 
Given  Iniliazie API service 
And add the parameters “from currency” , “ to currency” and “amount” 
Then add the generated api key  
When Api is invoked for the given data  
Then Verify and validate the response after conversion is valid  
Input Data :  
amount |  FromCurrency |  ToCurrency 
10 | INR | NOK 
200| NOK | USD 
https://api.apilayer.com/fixer/convert?from=NOK&amp;to=USD&amp;amount=200&amp;apikey=Dpma1c4vi7EQkVBc0ZLObWf9wIHpK5lm 
{     "success": true,     "query": {         "from": "NOK",         "to": "USD",         "amount": 200     },     "info": {         "timestamp": 1661520425,         "rate": 0.103936     },     "date": "2022-08-26",     "result": 20.7872 }  
Test case status :  pass

## Scenario 5 : Try to convert the amount with special character and verify it’s getting converted to specified currency 
Given  Iniliazie API service  
And add the parameters “from currency” , “ to currency” and “amount” 
Then add the generated api key  
When Api is invoked for the given data  
Then Verify and validate the response after conversion is valid  
Input Data :  
amount |  FromCurrency |  ToCurrency 
10$ | USD | NOK  
https://api.apilayer.com/fixer/convert?from=USD&amp;to=NOK&amp;amount=10$&amp;apikey=Dpma1c4vi7EQkVBc0ZLObWf9wIHpK5lm
{     "success": false,     "error": {         "code": 403,         "type": "invalid_conversion_amount",         "info": "You have not specified an amount to be converted. [Example: amount=5]"     } }  
Test case status :  pass

## Scenario 6 : Try to convert the amount with alphabets and verify it’s getting converted to specified currency 
Given  Iniliazie API service 
And add the parameters “from currency” , “ to currency” and “amount” 
Then add the generated api key  
When Api is invoked for the given data  
Then Verify and validate the response after conversion is valid  
Input Data :  
amount |  FromCurrency |  ToCurrency 
10kr     | NOK | INR 
200rs     | INR | USD  
https://api.apilayer.com/fixer/convert?from=USD&amp;to=NOK&amp;amount=10kr&amp;apikey=Dpma1c4vi7EQkVBc0ZLObWf9wIHpK5lm
{     "success": false,     "error": {         "code": 403,         "type": "invalid_conversion_amount",         "info": "You have not specified an amount to be converted. [Example: amount=5]"     } } 
Test case status :  pass 

## Scenario 7 : Try to convert the amount with alphabets and verify it’s getting converted to specified currency 
Given  Iniliazie API service  
And add the parameters “from currency” , “ to currency” and “amount” 
Then add the generated api key  
When Api is invoked for the given data  
Then Verify and validate the response after conversion is valid  
Input Data :  
amount |  FromCurrency |  ToCurrency 
10kr     | NOK | INR 
200rs     | INR | USD  
https://api.apilayer.com/fixer/convert?from=USD&amp;to=NOK&amp;amount=10kr&amp;apikey=Dpma1c4vi7EQkVBc0ZLObWf9wIHpK5lm  
{     "success": false,     "error": {         "code": 403,         "type": "invalid_conversion_amount",         "info": "You have not specified an amount to be converted. [Example: amount=5]"     } }  Test case status :  pass


## Scenario 8 : Try to add the amount and try to convert NOK to INR
Given  Iniliazie API service 
And add the parameters “from currency” , “ to currency” and “amount”
Then add the generated api key 
When Api is invoked for the given data 
Then Verify and validate the response after conversion is valid 
Input Data : 
amount |  FromCurrency |  ToCurrency
10+10kr     | NOK | INR

https://api.apilayer.com/fixer/convert?from=NOK&to=INR&amount=10+10&apikey=Dpma1c4vi7EQkVBc0ZLObWf9wIHpK5lm
{
    "success": false,
    "error": {
        "code": 403,
        "type": "invalid_conversion_amount",
        "info": "You have not specified an amount to be converted. [Example: amount=5]"
    }
}

Test case status :  pass

## Scenario 9 : Try to convert roman letter from NOK to INR
Given  Iniliazie API service 
And add the parameters “from currency” , “ to currency” and “amount”
Then add the generated api key 
When Api is invoked for the given data 
Then Verify and validate the response after conversion is valid 
Input Data : 
amount |  FromCurrency |  ToCurrency
XII     | NOK | INR

https://api.apilayer.com/fixer/convert?from=NOK&to=INR&amount=XII&apikey=Dpma1c4vi7EQkVBc0ZLObWf9wIHpK5lm
{
    "success": false,
    "error": {
        "code": 403,
        "type": "invalid_conversion_amount",
        "info": "You have not specified an amount to be converted. [Example: amount=5]"
    }
}

Test case status :  pass

## Scenario 10 : Try to convert Negative number from NOK to INR
Given  Iniliazie API service 
And add the parameters “from currency” , “ to currency” and “amount”
Then add the generated api key 
When Api is invoked for the given data 
Then Verify and validate the response after conversion is valid 
Input Data : 
amount |  FromCurrency |  ToCurrency
-10     | NOK | INR
-200    | USD | INR

https://api.apilayer.com/fixer/convert?from=NOK&to=INR&amount=-10&apikey=Dpma1c4vi7EQkVBc0ZLObWf9wIHpK5lm
{
    "success": false,
    "error": {
        "code": 403,
        "type": "invalid_conversion_amount",
        "info": "You have not specified an amount to be converted. [Example: amount=5]"
    }
}

Test case status :  pass


