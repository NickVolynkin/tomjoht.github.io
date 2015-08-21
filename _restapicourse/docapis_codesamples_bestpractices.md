---
title: Code sample best practices
permalink: /docapis_code_sample_bestpractices/
categories:
- api-doc
keywords:
course: "Documenting REST APIs"
weight: 2.7
type: notes_docapis
---
{% include notes.html %}

As you write documentation for developers, you'll start to include more and more code samples. You might not include these more detailed code samples with the endpoints you document, but as you create tasks and more sophisticated workflows about how to use the API to accomplish a variety of tasks, you'll end up leveraging different endpoints and showing how to address a variety of scenarios.

Here are some best practices around code samples.

## Code samples are like candy for developers

Code samples play an important role in helping developers use an API. What screenshots are to GUI documentation, code samples are to developer documentation. No matter how much you try to explain and narrate *how*, it's only when you *show* that developer truly get it.

## You are not the audience

Recognize that, as a technical writer rather than a developer, you aren't your audience. Developers aren't newbies when it comes to code. But different developers have different specializations. Someone who is a database programmer will have a different skill set from a Java developer who will have a different skillset from a front-end JavaScript developer, and so on.

Developers often make the mistake of assuming that their developer audience has a skill set similar to their own, without recognizing different developer specializations. Developers will often say, "If the user doesn't understand this code, he or she shouldn't be using our API." It might be important to remind developers that a tech savvy developer-user might welcome the extra detail in instructions.

## Focus on the why, not the what

In any code sample, you should focus your explanation on the *why*, not the *what*. Explain why you're doing what you're doing, not the detailed play-by-play of what's going on.

Here's an example of the difference:

* **what**: In this code, several arguments are passed to jQuery's `ajax` method. The response is assigned to the data argument of the callback function, which in this case is `success`.
* **why**: Use the `ajax` method from jQuery because it allows cross-origin resource sharing (CORS) for the weather resources. In the request, you submit the authorization through the header rather than including the API key directly in the endpoint path.

## Focus your explanation on your company's code only
In the above Mashape code, developers unfamiliar with the `.ajax()` method should consult [jQuery's documentation](http://api.jquery.com/jquery.ajax/). You shouldn't write your own version of jQuery documentation. Instead, focus on the parts of the code unique to your company. Let the developer rely on other sources for the rest (feel free to link to other sites).

## Keep code samples simple

Code samples should be stripped down and as simple as possible. In the Mashape code above, providing code for an entire HTML page is probably unnecessary. But including it doesn't hurt anyone, and for newbies it can help them see the big picture.

Avoid including a lot of styling or other details in the code that will potentially distract the audience from the main point. The more minimalist the code sample, the better.

When developers take the code and integrate it into a production environment, they will make a lot of changes.

## Add both code comments and before-and-after explanations

Your documentation regarding the code should mix code comments with some explanation either after or before the code sample. In the Mashape example, the code comments are set off with forward slashes `/` in the code.

Comments within the code are usually short one-line notes that appear after every 5-10 lines of code. You can follow up this code with more robust explanations later.

This approach of adding brief comments within the code, followed by more robust explanations after the code, aligns with principles of progressive information disclosure that help align with both advanced and novice user types.

## Make code samples copy-and-pastable

Many times developers will copy and paste code directly from the documentation into their application. Then they will usually tweak it a little bit for their specific parameters or methods.

Make sure that the code works. When I first used this Mashape code above, `dataType` was actually spelled `datatype`. As a result, the code didn't work (it returned the response as text, not JSON). It took me about 30 minutes of looking troubleshooting before I consulted the `ajax` method and realized that it should be `dataType` with a capital `T`.

Ideally, test out all the code samples yourself. This allows you to spot errors, understand whether all the parameters are complete and valid, and more. Usually you just need a sample like this to get started, and then you can use the same pattern to plug in different endpoints and parameters. You don't need to come up with new code like this every time.

## Provide a sample in your target language

With REST APIs, developers can use pretty much any programming language to make the request. Should you show code samples that span across various languages?

Providing code samples is almost always a good thing, so if you have the bandwidth, follow the examples from Evernote and Twilio. However, providing just one code example in your audience's target language is probably enough. You could also skip the code samples altogether, since the approach for submitting an endpoint follows a general pattern across languages.

Remember that each code sample you provide needs to be tested and maintained. When you make updates to your API, you'll need to update each of the code samples across all the different languages.

## From code samples to real tasks in user guides

Getting into code samples leads us more toward user guide tasks than reference tasks. Up until now, we've been focusing on reference documentation for REST APIs. The other section of the REST API documentation consists of user guide material.

In the user guide, you provide documentation for actual tasks that developers might do with the API. These tasks might involve using multiple API endpoints in particular sequences that demonstrate how to accomplish business goals and needs.