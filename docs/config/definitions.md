# 📄 Definitions

## Elements
### Position
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

#### Applicable to
All elements and divs, required.

### Size
Size has two required fields: `width` and `height`, it allows for the same modifiers as position.
```json
position {
    width = "16px"
    height = "5%"
}
position {
    width = "50% + 45px"
    height = "6px + 2%"
}
```

#### Applicable to
All elements and divs, not required for all elements

### Canvas

#### Applicable to
Everything with a changeable texture. Can be animated.

### Color

#### Applicable to

### Actions

#### Applicable to

### Text

#### Applicable to