# CSSGridSys
A simple, pure–CSS grid–system based on CSS–grid. This system allows for more complex layouts, using (for example) inline grids.

## Why?
CSSGridSys is responsive, easy to tailor to your specific needs, very open and it supports the continuity of the grid, **inside** grid elements.

## How?
The basic syntax of CSSGridSys works as follows:

    SCREEN_SIZE-col-COL_SIZE

Where *SCREEN_SIZE* can be either *s*, *m*, *l* or *xl* and *COL_SIZE* can range from *one* to *twelve* (in words). 

For example, an element that is 6 columns wide, would look like this:

    <el class="s-col-six"></el>

These elements are nested inside a ‘grid’ parent-element, like so:

    <parent class="grid s-col-six">
        <child class="s-col-six"></child>
    </parent>

### Responsive
Like you may be used to, CSSGridSys works with multiple definitions of screen-sizes and their respective column-sizes on the same element. If you want to create an element that is 6 columns wide on mobile sizes, and only 4 columns wide on desktop  sizes, you can add up the classnames like so:

    <el class="s-col-six m-col-four"></el>

This system can be applied to both parent and child elements, like so:

    <parent class=“s-col-six m-col-twelve”>
        <child class=“s-col-six m-col-four”></child>
        <child class=“s-col-three m-col-four”></child>
        <child class=“s-col-three m-col-four”></child>
    </parent>
    
The above code block will result in a six-column main-grid on mobile sizes, containing a full-width and two half-width elements inside. On larger sizes, it will be a 12-column grid with 3 equally sized columns inside.

### Inline grids
If your layout is slightly more complex or calls for parent elements defining interactions, CSSGridSys allows for inline grids that follow the original grid size by simply adding a “grid” class to any child-element, like so:

    <grandparent class=“s-col-six”>
        <parent class=“s-col-four grid”>
	          <child class=“s-col-three”>three column wide element</child>
	          <child>one-column wide element</child>
        </parent>
        <parent class=“s-col-two”></child>
    </grandparent>
    

### Offsets
If you want to offset an element, you use the following basic syntax:

    SCREEN_SIZE-offset-OFFSET_SIZE
    
Where, again, *SCREEN_SIZE* can be either *s*, *m*, *l* or *xl*, and *OFFSET_SIZE* ranges from *one* to *eleven* (in words).

An element that is six columns wide, with an offset of 3 columns, would then look like so:

    <el class=“s-col-six s-offset-three”></el>
    
