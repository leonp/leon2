---
title: "Principles for building good web forms"
category: web
---

Most websites have forms. Most forms are horrible to use. Some thoughts on how to make forms less horrible.

## What we want to achieve: accessible, usable forms and a good UX

Forms are great: write some HTML, publish it to a web server and wait for submissions. What could be simpler and more efficient for website owners?

But there is a downside. Forms can be frustrating to complete, for several reasons:

- It takes some manual dexterity to position a cursor within an input field with a mouse
- Moving between a mouse and a keyboard for textual input is a tiresome process
- Moving between fields is also a tiresome process
- Some types of inputs (such as dropdown lists using the `select` and `option` elements) are fiddly and/or repetitive to use
- Spam prevention such as Captcha is frustrating to use
- Wording and UI can be surprisingly difficult to get right

Multiply these problems by ten if your user is completing the form on a phone.

A good starting point for building forms is acknowledging they are difficult for users. Armed with this truth, we can mitigate these problems by following a few principles.

## Request the minimum amount of information and no more

Each move between fields, each letter typed, each label to interpret is an extra piece of work for the user. Therefore, only ask for the information you need. Where possible, merge related fields into one. For example, unless you need to specifically address a user with a surname or forename, use a `Name` field rather than separate `First name` and `Surname fields` (this will also make it easier for people whose names don't fit into this format).

## Avoid compulsory/optional fields if possible

In theory, if you're requesting the minumum amount of information all fields will be complulsory by definition. You'll save your users having to work out whether they should enter information in optional fields. Even if they are filling in every field because they haven't interpreted your optional/compulsory UI, you're saving them work.

## Make fields optional rather than compulsory

I was testing some forms yesterday and was surprised to see one user struggle with the meaning of the red asterixes by some labels. Red asterixes denoting a compulsory field are a convenient shorthand; however, they are a convention, and rely on the user having learnt that convention.

You might argue some explanatory text at the top of the form would help here. It might, but you're relying on the user spotting this text and interpreting it correctly. The first rule of all web design is users don't read.

Red stars and words like <i>compulsory</i> are all very imperative. Make your tone more polite by reversing the approach. Instead of marking compulsory fields with a red asterix, add the word <i>optional</i> to non-compulsory field labels.

## Use label fors and associated input IDs

Sighted users can (usually) figure out which labels apply to which form fields. To make the relationship explicit to non-sighted users, make sure your `label` contains a `for` element that matches its associated `input`'s `id` attribute. For example:

{% highlight html %}
{% raw %}
<label for="email-address">Email</label>
<input type="email" id="email-address">
{% endraw %}
{% endhighlight %}





1. Principle 1: Completing forms online is a horrible experience, especially on a phone
2. Use labels and associated IDs
3. Styling input fields (bigger than fields, padding, prximity to label)
4. Buttons to submit
5. Honeypots (visible or not visible)
6. Use input type attributes
9. Only use the minimum number of fields (all fields should be compulsory)
7. Don't use placeholders
9. Don't put the submit button in the input field
8. Don't use compulsory, use optional instead
