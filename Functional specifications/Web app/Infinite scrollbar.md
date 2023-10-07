# Functional specifications: infinite scrollbar
## Scrolling
The infinite scrollbar must provide the user a control to navigate forward and backward in a collection that is so large that a normal scrollbar would be uneasy to control.

It consists of a handle by default sticking to the center of the scrollbar which when grabbed to the left navigate backward in the collection.  
The further away from the center, the quicker it scrolls.  
When grabbed to the right, it navigates forward the same way.  
When the handle is dropped, it return to its default centered position on the scrollbar.  
The nearest step to the center should in- or decrement the collection by $\frac{1}{\textit{refresh rate}}$ unit every refresh, while the furthest step should in- or decrement the collection by $\frac{\textit{collection size}}{\textit{refresh rate}}$ every refresh.  
The in between steps must be interpolated exponentialy.  
A reasonable deadzone must lie around the center of the scrollbar.

For a $\textit{refresh rate}$ of $60\text{Hz}$, this would be a displacement of $\frac{\textit{collection size}}{60}$ every $1\div60 \approx 16.7\text{ms}$, giving a maximum displacement speed of the whole collection size in 1 second.  

## Applied to time
As the calendar has a given time representation with most likely multiple numbers, the above functioning should be repeated for each time division.
Given a calendar with a time representation using $n$ divisions, each half of the infinite scrollbar is divided into $n$ divisions.  
With $d_\text{max n}$ the maximum number for the division $n$, the nearest point to the default position should in- or decrement by $\frac{1}{\textit{refresh rate}}$ unit of $n$ per refresh and the furthest point should in- or decrement by $\frac{d_\text{max n}}{\textit{refresh rate}}$ every refresh.

For the gregorian time representation, the scrollbar is divided into 12 divisions (plus the 13th default position) with maximum displacement per division: years (-1000, arbitrary), months (-12), days (-31), hours (-24), minutes (-60), seconds (-60), zero (no displacement), seconds (+60), minutes (+60), hours (+24), days (+31), months (+12), years (+1000, arbitrary).
