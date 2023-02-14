# yUML Extension Demo

This is a set of yUML files to demonstrate the yUML language and [VSCode Extension](https://github.com/jaime-olivares/vscode-yuml). Together, they form an easy-to-use way to generate programming diagrams from code.

- [yUML](http://yuml.me/) is an extended UML diagram programming language
- [vscode-yuml](https://github.com/jaime-olivares/vscode-yuml)

## Running/Generating

Once you have the VSCode extension installed, you can easily preview any yuml file by clicking the "Preview yUML diagram" icon button in the top right.

### Generating SVGs

You can automatically generate svg files everytime you preview yUML files by adding `// {generate:true}` to your yUML file.

Alternatively, you can click+drag a preview image to your desktop. Tip: if you're VSCode is using a dark theme, you can export a dark-version of the yUML using the click-drag method.

### Generating PNGs

The best known way is to convert a generated SVG.

Two methods:

1. With your OS system tools (i.e. Preview for Mac)
2. With librsvg:

    ```bash
    brew install librsvg
    rsvg-convert -h 800 test-class.svg > test-class.png
    ```

## Directives

```yuml
// {direction:leftToRight|topToBottom}
// {generate:true}
// {type:class|sequence|usecase}
```

## Class

```yuml
[Customer]->[Order]               // Association
[Customer]<>->[Order]             // Aggregation
[Customer]++->[Order]             // Composition
[Customer]1-0..1>[Order]          // Cardinality
[Customer]1-0..orders 1>[Order]   // Assoc Labels
[Customer]-.-[note: DAO]          // Notes
[Customer]^[Member]               // Inheritance
[Customer|name;address|save()]    // Properties
[≪IDisposable≫;Customer]          // Interface
[Customer|var arr［］ ]            // Brackets
[Customer {bg:green}]             // Colour
```

## Use Case

```yuml
[Customer]                        // Actor
[Customer]-(Place Order)          // Actor to Use Case
(Order)>(Cancel)                  // Extend
(Order)<(Pay)                     // Include
[Member]^[Customer]               // Actor Inheritance
```

## Notes

```yuml
[note: You can stick notes on diagrams too!{bg:wheat}]
[Customer]-[note: A note attached to an element]
```
