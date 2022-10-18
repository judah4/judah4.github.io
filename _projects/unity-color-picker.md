---
layout: page
title:  "Unity Color Picker"
image: "/assets/img/projects/color-picker.png"
type: Open Source Project
draft: false
order: 0
---
Type: {{page.type}}  

![Screenshot]({{page.image}})

My contribution to unity developers who need a color picker to use in their games in unity.

[GitHub Page](https://github.com/judah4/HSV-Color-Picker-Unity) 

#### Example of hooking up the event listener
```CSharp
public Renderer renderer;
public ColorPicker picker;
 
// Use this for initialization
void Start ()
{
    picker.onValueChanged.AddListener(color =>
    {
        renderer.material.color = color;
    });
    renderer.material.color = picker.CurrentColor;
}

// Update is called once per frame
void Update () {

}
	
```

#### Example of setting the color in code.
```Csharp
Color color = Color.green;
picker.CurrentColor = color;
```
