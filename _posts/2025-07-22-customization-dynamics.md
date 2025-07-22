---
layout: default
title: Mastering Multi-Select Fields and Conditional Logic in Dynamics CRM
---

### Introduction  
Microsoft Dynamics CRM 365 offers powerful customization capabilities that let businesses tailor their workflows and forms. This article explores how to use multi-select option sets and dynamically show/hide fields using JavaScript.

### Problem Scenario  
Imagine a form where users select multiple services. Based on their selection, relevant fields must appear—without cluttering the interface.

### Sample Code  
```javascript
function toggleFieldsBasedOnSelection(executionContext) {
    var formContext = executionContext.getFormContext();
    var selectedOptions = formContext.getAttribute("new_services").getSelectedOption();

    if (selectedOptions.includes("Consulting")) {
        formContext.getControl("new_consultingDetails").setVisible(true);
    } else {
        formContext.getControl("new_consultingDetails").setVisible(false);
    }
}
