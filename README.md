# nightmare-automation-ui-testing

When I had to work on UI automation proof of concept using nightmarejs automation library , I thought to choose one web application that can expose most of the nightmarejs usage methods , potential pit falls and limitations 

Arunkumar muralidharan at Qxf2 suggested me to use https://weathershopper.pythonanywhere.com application which he has developed for training purpose on QA automation. Their goal was to develop a small web application that can help testers learn automation tool which can expose most of the programming challenges with respect to automation in one go 

I must say his application helped me in understanding and doing thorough proof of concept for nightmarejs tool 

I thought sharing nightmare automation work can help others who wants to explore nightmarejs tool for UI automation purpose   


# nightmarejs setup

Have the nodejs(https://nodejs.org/en/) installed for your os 

$ npm install --save nightmare

To run these tests you need to install mocha testframe work too

$ npm install --save-dev mocha 


Automating http://weathershopper.pythonanywhere.com/ use cases using nightmarejs

1. Go to home page - Done
2. Check temperature value and hint text - Done
3. Based on hint text navigate to moisturizers or sunscreens shopping page - Done
4. Add products to cart based on hint text conditions - Done
5. Submit cart product with some test stripe card details - Not Done

# nightmare limitations

Listed down some of the nightmarejs pitfalls and limitations that I have come across during the Nightmare.js automation proof of concept using weathershopper.com test application  

1. nightmare instance inside a loop does not work(it returns first iteration results for every iteration),
need to use work around like Array.reduce (Vanilla JS) or vo

https://github.com/rosshinkley/nightmare-examples/blob/master/docs/common-pitfalls/async-operations-loops.md

2. document.queryselectAll() does not return web elements using nightmare unless mapping it to some attribute 
(DOM elements and DOM element lists are not serializable) 

https://github.com/segmentio/nightmare/issues/567#issuecomment-209533871
https://github.com/segmentio/nightmare/issues/1500

3. Getting the global variables inside the nightmare evaluate scope is not straight forward

https://github.com/segmentio/nightmare/issues/89

4. Nightmare does not pass element attributes outside the nightmare scope, one of the work around is to save the nightmare response and reuse 

https://github.com/rosshinkley/nightmare-examples/blob/master/docs/known-issues/globally-defined-variables.md

5. Nightmare function 'evaluate' will return value only to 'then' caller

https://github.com/segmentio/nightmare/issues/1131

6. Asynchronous operations can lead to simultaneous calls causing early returns with wrong results

https://github.com/segmentio/nightmare/issues/493

7. Need to install nightmare iframe manager separately to work with iframe

https://github.com/rosshinkley/nightmare-iframe-manager 


# nightmare test run

npm test

![ nightmare test run screenshot ](https://github.com/rajiqxf2/nightmare-automation-ui-testing/blob/master/images/nightmare-test-run.png)
