---
layout: layouts/post.njk
title: Contact Me
templateClass: tmpl-post
eleventyNavigation:
  key: Contact Me
  order: 6
---


<form name="contact" method="POST" data-netlify="true">
    <p>
        <label>Full Name: <input type="text" id="name" name="name" required minlength="4" /></label>   
    </p>
    <p>
        <label>Email Address: <input type="email" id="email" name="email" pattern=".+@mail\.com" required autocomplete minlength="6" multiple /></label>
    </p>
    <p>
        <label>Message: <textarea name="message" required></textarea></label>
    </p>
    <p>
        <button class="form_submit" type="submit">Send</button>
    </p>
</form>
<script>
    //get default border colours (to use on input when validation passes)
    var borderStylePass = document.querySelector('#name').style.border;
    //set fail border colours (to use on input when validation fails)
    var borderStyleFail = '1px solid red';
    //get the form submit button
    var submit_button = document.querySelector('.form_submit');
    //attach form event listener
    submit_button.addEventListener("click", function(event){
        //get the form "name" element
        var name = document.querySelector('#name');
        //get the form "email" element
        var email = document.querySelector('#email');
        //all validation is assumed to be passed until tested
        blnValidated = true;
        //change the border as it the validation passed
        name.style.border = borderStylePass;
        //if validation fails change the bln to false and change the input border colour
        if(!name.value){
            blnValidated = false;
            name.style.border = borderStyleFail;
        }
        //if validation fails change the bln to false and change the input border colour
        email.style.border = borderStylePass;
        if(!email.value){
            blnValidated = false;
            email.style.border = borderStyleFail;
        }
        //if validation failed do not allow the form to submit the data
        if(!blnValidated){
            event.preventDefault();
        }
    }, false);
</script>