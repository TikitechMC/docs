---
sidebar_position: 1
---

# 🔨 First Menu
Creating a menu is really simple with Sunscreen! We'll go through the neccesary steps for your first (fullscreen) menu.  

## 📁 The file
Sunscreen doesn't use YML but [HOCON](https://github.com/lightbend/config/blob/main/HOCON.md) instead. This choice was made because of the decreased readability YML has with lots of nested elements and the possible indentation errors that come with it.  

For further explanations on the behavior of config elements, please consult the [definitions](/docs/definitions) page

### Required
A menu config always requires the following entries
```json
identifier = "sunscreen:test_menu"
type = "float"
```
#### Identifier
All elements, divs, menus and more use identifiers. Identifiers are made up of a namespace and a key, seperated by a `:` character. This choice has been made to keep elements and menus from clashing with each other, while also making clear what the origin of an element is.

#### Type
The type corresponds to the way a menu is rendered, the current version of Sunscreen only supports the `float` type.

### Div
A div is comparable to a layer in photoshop, or the similarily named element type from web development languages. Divs contain elements, which are rendered as a whole on the div canvas, they cannot go beyond the size set for the div.

Divs always require the following entries
```json
identifier = "planet:main_div"
position {
    x = "0%"
    y = "0%"
}
elements {
    ...
}
```

#### Position
The position section always requires both the `x` and `y` value to be defined, either in percentages, pixels or a mix of both.  
Example positions could look like the following
```json
position {
    x = "16px"
    y = "5%"
}
position {
    x = "50% + 45px"
    y = "6px + 2%"
}
```

### Elements
Elements are the backbone of menu visuals, while also being interactable.  
There are many types of elements, with the possibility to add your own using the [API](/docs/api).  
A list of default elements is given below
| Name | Id | Description | Interactable | Arguments |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| Image | image | Simple image element, can show images from files or urls. | No | [Canvas](/docs/config/definitions#canvas), [Position](/docs/config/definitions#position) |
| Button | button | Simple clickable image element, has both hover and click events. | Yes | [Canvas](/docs/config/definitions#canvas), [Position](/docs/config/definitions#position) |
| Dropdown | dropdown | Compact element with dropdown selector list. | Yes | [Canvas](/docs/config/definitions#canvas), [Position](/docs/config/definitions#position) |
| Selector | selector | Multiple buttons, either vertical or horizontal with max 1 selected. | Yes | [Canvas](/docs/config/definitions#canvas), [Position](/docs/config/definitions#position) |
| Shape | shape | Simple single color filled shape. | No | [Canvas](/docs/config/definitions#canvas), [Position](/docs/config/definitions#position) |
| Text | text | Simple text implementation. | No | [Canvas](/docs/config/definitions#canvas), [Position](/docs/config/definitions#position) |
| Text Input | text_input | Text box that allows for usable text input. | Yes | [Canvas](/docs/config/definitions#canvas), [Position](/docs/config/definitions#position) |

#### Usage
Using an element is as easy as giving 