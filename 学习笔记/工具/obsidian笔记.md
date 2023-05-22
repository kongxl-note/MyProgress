
# obsidian笔记
## 1、插件安装

- 笔记目录下`.obsidian`目录下新建目录`plugins`
- 在`plugins`目录创建各插件目录（目录名与插件名称一致）


![[attachments/Pasted image 20230521234347.png]]
- 插件目录中存放

![[attachments/Pasted image 20230521234521.png]]

## 2、 插件的使用

### obsidian-desmos

#### Usage

The most basic usage of this plugin involves creating a codeblock with the tag `desmos-graph` and placing the equations you wish to graph in the body:

```
    ```desmos-graph
    y=x
    ```
```

View Graph

Equations use the [LaTeX math](https://en.wikibooks.org/wiki/LaTeX/Mathematics) format and you can graph multiple equations by placing each one on a seperate line:

```
    ```desmos-graph
    y=\sin(x)
    y=\frac{1}{x}
    ```
```

View Graph

You can restrict the bounds of the graph and apply other settings by placing a `---` seperator before your equations. The content before it must be a set of `key=value` pairs seperated by either **newlines or semicolons** (or both):

```
    ```desmos-graph
    left=0; right=100;
    top=10; bottom=-10;
    ---
    y=\sin(x)
    ```
```

View Graph

You can set the dimensions of the rendered image by using the `height` and `width` fields.  
Additionally, you can disable the graph grid by setting `grid=false`.

You can set the mode of trigonometry functions by using the `degreeMode` setting.  
This has two valid values: `radians` or `degrees`. By default, it will be set to `radians`.

##### [](https://github.com/Nigecat/obsidian-desmos#equation-control)Equation Control

You can additionally set three other fields for each equation - the style, color, and a restriction. Each of these must be placed between a series of `|` characters after the equation (in any order).

The valid colors are (case-insensitive):

-   `RED`
-   `GREEN`
-   `BLUE`
-   `YELLOW`
-   `MAGENTA`
-   `CYAN`
-   `PURPLE`
-   `ORANGE`
-   `BLACK`
-   `WHITE`
-   Any hex color code beginning with `#` (e.g `#42ddf5`)

Note that the default color can be set by using the `defaultColor` field in the graph settings. This field follows the same format.

The valid styles are (case-insensitive):

-   Line (e.g `y=x`)
    -   `SOLID` (default)
    -   `DASHED`
    -   `DOTTED`
-   Point (e.g `(1,4)`)
    -   `POINT` (default)
    -   `OPEN`
    -   `CROSS`

For example, if we wanted to create a straight green dashed line of `x=2` with a restriction of `y>0` we could do any of the following.

```
    ```desmos-graph
    x=2|y>0|green|dashed
    ```
```

```
    ```desmos-graph
    x=2|y>0|dashed|green
    ```
```

```
    ```desmos-graph
    x=2|green|y>0|dashed
    ```
```

```
    ```desmos-graph
    x=2|dashed|green|y>0
    ```
```

(you get the idea)

View Graph

Additionally, individual equations can be hidden with the `hidden` flag, this can be useful when graphing things such as derivatives:

```
    ```desmos-graph
        f(x)=x^2|hidden
        f'(x)
    ```
```

View Graph

###### [](https://github.com/Nigecat/obsidian-desmos#labels)Labels

Point labels can be specified with the `label:<content>` flag (equation labels are unsupported by Desmos):

```
    ```desmos-graph
        (0,0)|label:(0,0)
        (5,4)|open|label:This is a label
    ```
```

View Graph

#### [](https://github.com/Nigecat/obsidian-desmos#custom-styling)Custom Styling

The `obsidian-desmos` CSS class is applied to all graphs. This can be used in themes and snippets to override certain behaviour.  
For instance, if you wanted all graphs to be centered in the page content, you could use the following snippet:

/* Horizontally center the graph in the page content */
.desmos-graph {
    display: block;
    margin-left: auto;
    margin-right: auto;
}

##### [](https://github.com/Nigecat/obsidian-desmos#offline-usage)Offline Usage

If you've rendered at least one graph while connected to the internet then any future graphs (irrespective of the cache setting) should be able to render (if they don't then make an issue here).  
*Requires enabling legacy API mode in the plugin settings.





### obsidian-functionplot



```functionplot
---
title: The random graph
xLabel: x
yLabel: y
bounds: [0, 10, 0, 50]
disbaleZoom: 1
grid: true
---
g(x)=x^PI
f(x)=E+log(x)*2
```
### text-snippets-obsidian

### obsidian-annotator