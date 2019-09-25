---
title: Widgets
weight: 1 
---

## Widget types 

Every widget has a type, which will determine its display. The type is included in the widget's name.

The available types are:

| Identifier |
|------------|
| box        |
| table      |
| bar        |

For example, `ga.bar_pages` is a widget attached to the service Google Analytics (`ga`), and it's a `bar` diagram.

Each type of widget has its own display options. Here's the exhaustive list:

## Box Widgets

| Name           | Description                             | Default value             | Examples                                  |
|----------------|-----------------------------------------|---------------------------|-------------------------------------------|
| title          | Title                                   | Depending on the widget   | ` Users `                                 |
| height         | Height                                  | `10`                      | `5`                                       |
| color          | Global color for title, border and text | `Default color`           | [colors](/display/colors)                 |
| title_color    | Title color                             | `Default color`           | [colors](/display/colors)                 |
| border_color   | Border color                            | `Default color`           | [colors](/display/colors)                 |
| text_color     | Text color                              | `Default color`           | [colors](/display/colors)                 |

## Table Widgets

| Name               | Description                             | Default value                   | Examples                                      |
|--------------------|-----------------------------------------|---------------------------------|-----------------------------------------------|
| title              | Title                                   | `Depending on the widget`       | `Users `                                      |
| color              | Global color for title, border and text | `Default color`                 | [colors](/display/colors)                     |
| title_color        | Title color                             | `Default color`                 | [colors](/display/colors)                     |
| border_color       | Border color                            | `Default color`                 | [colors](/display/colors)                     |
| text_color         | Text color                              | `Default color`                 | [colors](/display/colors)                     |

## Bar Widgets

| Name              | Description                                                     | Default value                 | Examples                                    |
| ----------------- | --------------------------------------------------------------- | ----------------------------- | ------------------------------------------- |
| title             | Title                                                           | `Depending on the widget`     | `Users `                                    |
| border_color      | Border color                                                    | `Default color`               | [colors](/display/colors)                   |
| height            | Height                                                          | `10`                          | `5`                                         |
| color             | Global color for title, border, text and every colored elements | `Default color`               | [colors](/display/colors)                   |
| title_color       | Title color                                                     | `Default color`               | [colors](/display/colors/)                  |
| text_color        | Text color                                                      | `Default color`               | [colors](/display/colors/)                  |
| num_color         | Color of numerical data                                         | `Default color`               | [colors](/display/colors/)                  |
| empty_num_color   | Color of numerical data when the bar is too small to appear     | `Default color`               | [colors](/display/colors/)                  |
| bar_color         | Bar color                                                       | `Default color`               | [colors](/display/colors/)                  |
| bar_gap           | Gap size between the bars                                       | `0`                           | `5`, `10`                                   |
| bar_width         | Bar width                                                       | `6`                           | `5`, `10`                                   |

