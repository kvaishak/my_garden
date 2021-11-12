---
title: Shortcomings of HTML Rendering
---

I was accepted for the position of Member technical staff for the team <a href="https://show.zoho.com/">Zoho Show</a> at Zoho corporation in June of 2017. Zoho Show is the Zoho’s answer to Google Slides in a feature-rich package. My first task as a Web Developer in Zoho show was to code a feature that allows the shapes drawn inside Show to have Inner/Outer Borders. Up until then, Zoho show had the option to just choose between different types of the border like dotted, dashed etc and to change their width, but not the alignment of the border concerning the shape.

# The problem

In HTML, an SVG element, be it a path, rectangle or a circle can have SVG stroke with the following properties.

- stroke
- stroke-width
- stroke-linecap
- stroke-dasharray

These properties can be used to modify various properties of SVG element like colour, stroke width, type of ending to an open path and they type of stroke respectively. But there is no property by which we can specify if a stroke should be aligned to the centre, inside or to the outside of a closed path.

<img src="/assets/stroke_types.png" />

<figure>
    <img src="/assets/stroke_types.png"  alt="Different stroke representation">
    <figcaption>Illustration showing the default(Center) stroke with the representation of inner/outer stroke for the shape with the same dimensions.<figcaption>
<figure>    
	
	
