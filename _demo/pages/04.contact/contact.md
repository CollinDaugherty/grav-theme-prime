---
title: Contact
widget:
    options: ''
form:
    name: contact
    fields:
        -
            name: name
            label: Name
            autocomplete: 'on'
            type: text
            validate:
                required: true
        -
            name: email
            label: Email
            type: email
            validate:
                required: true
        -
            name: budget
            type: text
            label: Budget
            validate:
                required: true
        -
            name: message
            label: Message
            type: textarea
            placeholder: null
            rows: 8
            validate:
                required: true
        -
            name: honeypot
            type: honeypot
    buttons:
        -
            type: submit
            value: Send
    process:
        -
            email:
                subject: '[Site Contact Form] {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: contact-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            message: 'Thank you for getting in touch!'
---

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad exercitationem odio doloremque nobis quo officia in tempore magni maxime.