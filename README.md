#jq-selected

Wish you could stye more than just :hover with CSS? 

Well, now you can style elements when they are clicked. 

jq-selected add classes to recently clicked items to boldly let CSS handle mundane tasks normally handled by javascript. 

## Whut? Why?

I got tired of scripting .click events in javascript for things like drop-down menus, tooltips, popups, modals, etc. 

jq-selected adds classes to recently clicked items so you easily can apply CSS -- and CSS animations!

When targeted item is clicked, it gets the class "selected" and either the class "odd" or "even" depending on the number of times it was clicked. 

###  Usage

Add this to your document.ready

    $(".foo").selected()
    
Foo can be whatever. 

Now, when .foo is clicked, it gets the class **selected** and either the class **odd** or **even** depending on the number of times it was clicked. 

###  Options

    $(".foo").selected({
       parent: '.bar',
       selectAll: false // default is true
    });
    


By default, other items that BEGIN with the same class you clicked (can be .foo or any other class) are toggled. You can disable this by setting the option selectAll to false.

You can also specify a parent selector to limit the scope of the selected item. 


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
	
	
