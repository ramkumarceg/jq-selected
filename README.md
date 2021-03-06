#jq-selected

Wish you could stye more than just :hover with CSS? 

Well, now you can style elements when they are clicked. 

jq-selected adds classes to recently clicked items and boldly lets CSS handle mundane tasks normally handled by javascript. 

## Whut? Why?

I got tired of scripting .click events in javascript for things like drop-down menus, tooltips, popups, modals, etc. 

jq-selected adds classes to recently clicked items so you can apply CSS -- and CSS animations!


###  Usage

Add this to your document.ready

    $(".foo").selected()
    
Foo can be whatever. 

Now, when .foo is clicked, it gets the class **selected** and either the class **odd** or **even** depending on the number of times it was clicked.

In the situation where a parent has .slected() and a child has .selected() as well, when the child is clicked the event does not bubble up to the parent. (basically, only the child's class is changed, not the parent)

###  Options

    $(".foo").selected({
       parent: '.bar',       
       targetClass: 'baz',    // name only do not include '.' identifier 
       selectAll: false       // default is true
    });
    

`parent` : Given the selector, (ie. `#id`, `.class`, `ul`), `parent` limits the scope of the selected item(s).

`targetClass` : accepts class name, (*Don't include the period in the class name*), and will toggle the selected class of the `targetClass`. Note: Useful for having a child element toggle its parent's state.

`selectAll` : By default, other items that BEGIN with the same class you clicked (can be .foo or any other class) are toggled. You can disable this by setting the option selectAll to false.


###  Styling


You can style the most recent clicked item with "even" or "odd" or all clicked items with the class"selected".


Styling could go something like this:

	.foo.selected {
		color: red;
	}
	
	.foo.selected.odd {
		color: blue;
	}
	
	.foo.selected.even {
		color: green;
	}
	
	
