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

<img src="/assets/stroke_types.png"  alt="Different stroke representation"/>
Illustration showing the default(Center) stroke with the representation of inner/outer stroke for the shape with the same dimensions.

# Solution

The easiest way to achieve the required inner/outer stroke effect in SVG would be using the clip-path.

**Inner Stroke** 
Creation of inner stroke for an SVG path is easy and involves two simple steps.

1. For getting an inner stroke of 10px, give the original shape a stroke of 20px(Double the required amount).
2. Use the path of the source SVG, as clip without any stroke and apply it to the original SVG path.

An example can be found <a href="https://codepen.io/wireshark47/pen/YzPwVrm">here</a>. Using this method we can get a clear inner stroke for any SVG path.

**Outer Stroke**

Outer stroke using clip-path is a bit tricky because of the nature of the clipping in SVG.

1. As in the case of inner stroke, give the original shape a stroke width, which is double your required amount.
2. Create a new SVG path, which contains the original shape path + a path of a bounding rectangle whose dimensions calculated such that the new shape including the doubled stroke should fall within the rectangle.
3. Use the above-created path as clip-path with the <code>clip-rule = “evenodd” </code>.

Using the above method the clip-path with clip the space inside the shape thereby hiding the inner portion of the stroke. Refer <a href="https://codepen.io/wireshark47/pen/QWwyvzq">here</a> for an example.

# The shortcoming of using clip-path
Even though using clip-path is one of the easiest and fastest ways to render a clean model of inner/outer stroke. It has its own disadvantages. Some of them are.

1. As shown in the example of outer stroke, It is possible only in case of SVG paths - For present shapes, one might have to convert them to SVG paths and then find out the appropriate clip-path.
2. Also, outer stroke rendering requires finding out a proper bounding rect from the original shape, which might require additional calculation.
3. In the case of open shapes, it's again difficult to determine the orientation of the stroke.
4. Shapes with intersecting paths might require additional steps of breaking down of the single complex shape into multiple shapes and performing the clipping action to each of the shapes.

# Conclusion
Using SVG clip-path one can render a clean inner/outer stroke thereby circumventing the lack of a much-needed requirement of a stroke-align properly in HTML.
		
