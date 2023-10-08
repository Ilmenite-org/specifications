# Functional specifications: event
Represent an event that occurred at some time.

## Time representation
The event must have a *Point in Time* field that represents the date and possibly time when it occurred.  
It should also have a duration that indicates the *accuracy* of the PiT (for example: more or less 1 day).

## Texts
Each text should be translatable.
### Name
The *name* or *title* of the event.
### Description
A short *description* as a rich text field.
### Links
*Links* to sources or other articles with their title.
### Categories
A list of *categories* to which the event belongs to.

## Space representation
### Point in space
The *point in space* where the event occurred, if any.  
The point in space representation should include its *referential* in order to represent point in any place of the universe (the Earth, solar system,...).
### Scope
The *scope* of the event, if any:  
if an event' scope is worldwide, it will be shown whatever the search place is set to, whereas if it takes place in the USA, it won't be shown for a search outside of the USA.
