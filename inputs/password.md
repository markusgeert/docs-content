---
title: Password Input
description: A native HTML password input.
---

::InputPageHero
---
type: "Password"
---
::

:PageToc

The `password` input uses HTML's [native password input](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/password). It allows a user to privately enter their password. When creating new passwords, this input is often compiled with the `confirm` validation rule.

## Example

::Example
---
name: "Password input"
file: "_content/_examples/password/password.vue"
---
::

### Toggle password visibility

By leveraging the [icons](/essentials/icons) support built in to FormKit you can easily create a password input where password visibility can be toggled. 

::Example
---
name: "Password input"
file: "_content/_examples/icons/handle-click.vue"
---
::


## Props & Attributes

The `password` input has no unique props but can make use of the following universal FormKit props.

::ReferenceTable
---
input: "password" 
attrs: ['maxlength', 'minlength', 'placeholder']
---
::


## Sections

:SectionKeysIntro

::FormKitInputDiagram
---
label-content: "Password"
prefix-icon-content: "🤫"
input-content: "···········"
suffix-icon-content: "🤐"
help-content: "Keep this hidden in a safe place."
message-content: "Password is required."
---
::

::ReferenceTable
---
type: "sectionKeys"
primary: "section-key"
---
::

