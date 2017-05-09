---
title: Contact
form:
    name: contact-form
    fields:
        -
            name: name
            label: Name
            autofocus: 'off'
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
            name: message
            label: Message
            type: textarea
            rows: 6
            validate:
                required: true
    buttons:
        -
            type: submit
            value: Submit
    process:
        -
            email:
                from: '{{ config.plugins.email.from }}'
                to: ['{{ config.plugins.email.from }}', '{{ form.value.email }}']
                subject: '[Feedback] {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: feedback-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
---

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad exercitationem odio doloremque nobis quo officia in tempore magni maxime.