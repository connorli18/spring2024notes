# [1/24] UIUX

### Grids

#### Intro

- Bauhaus School of Design $\rightarrow$ mass production with aesthics and everyday function
  - This inspired Grid Layouts, underlying organization of information placement

#### Groups

- How to create groups?
  - Groups are created via columns and rows (in grids)
- How do we use location?
  - Put the information in the upper-left grid cell
- How do we use size?
  - Make the column bigger
- How do we use whitepsace to make a group seem more important?
  - You can make the grid differences larger/smaller (increase/decrease the size of the gutters)

#### Grids

- Web Browsers are in charge of rendering HTML
- When you use a new element, does it obey or break line-wrap layout? 
- Use an iterative style of programming.

#### Design Steps (Facebook)

1. Make an HTML page, connect some CSS
2. Make a container div (to contain everything).
3. Give container div realistic width, and keep all design in the CSS file.
4. Get header height (Add padding, etc.)
5. Add the first post (everything else not in the div header)
   1. DIV elements will flow down the page. *display: block*
   2. To get them to flow across the page, you must set *display: inline-block*
6. Add padding to the Top Post
7. Reply substructure: image and text
8. Reply Class background-color
9. Borders add 1px $\rightarrow$ could overflow

#### Examples

- Gmail has grids, YouTube has grids
- Twitter Bootstrap grids, 12 grids and grids within grids
  - Grids vs. Padding?
- Twitter Bootstrap (also solves the issue of the mobile devices)

```
<div class = "col-md-2 col-sm-6">
 	<!---- On a medium device, This means that it is a column of 2/12 ---->
 	<!---- On a small device, this means that it is a column of 6/12 ---->
</div>
```

