---
title: Templated Rating
page_title: Templated Rating
position: 4
slug: templated-rating
---

# Overview

The **RadTemplatedRating** component is designed to be used in the cases where it is easier to provide a template (e.g. just an image) for the rating items instead of creating custom **RadPathGeometry**. On top of the API of the [RadRatingBase]({% slug rating-base %}) this component adds the following members:

 - (DataTemplate) **ItemTemplate** - Gets or sets the template used in the rating item.
 - (DataTempalte) **SelectedItemTemplate** - Gets or sets the template used in the selected rating item.

> Both templates should be set in order the control to function as expected.



Here is how the rating component can be setup:

<snippet id='rating-templates'/>

![](images/rating-templates.png)