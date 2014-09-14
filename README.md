# Masseuse Multiple Select Component

Masseuse Multiple select is a [masseuse](https://github.com/Solid-Interactive/masseuse) plugin that will display a dropdown with search where selections are made via checkboxes these changes are synces with a masseuse collection, toggling any property on the collections models.

Uses the [polymer](http://www.polymer-project.org/) library for shadow dom and binding.


## How To Use:
```html
<masseuse_multiple_select collection="someMasseuseCollection">
</masseuse_multiple_select>
```

## Important Things to notice about the example above :
  * The syncing with the collection is done anytime an item is checked via toggling a 'checked' property on the model. This 'checked' property is only a default and can be overridden as evidenced below. If the property is not allready there, it will be added as false(unchecked) when initialized. So, if you want to have the checkbox appear initially as checked, ensure this property is true. You might do this with computed properties. 
  * The collection will recieve a `.$select` propety that will maintain a refernce to the instance.
  * The tag is replaced with an instance of multiple-select. So any additional styling you want to apply to the tag should be done with the normal `class` attribute.
  * The `masseuse_multiple_select` can have inner html and this will be used instead of the standard checkbox format. Putting any html in here will negate the `label` attribute on the parent tag. This will all be wrapped in the `<label>` tag of the checkbox, so any clicks inside (if allowed to propagate) will toggle the checkbox.
  
## Events  
  * The child models and parent collection can expect all of the same events associated with a `masseuseModel.set()`, which currently is still identical to the standard [backbone](http://backbonejs.org/) events.
  * Other events that you can expect to see on the masseuse collection:
    * onCheckAll - Fires when all the options are toggles by either clicking the “Select all” checkbox, or when the “checkall” method is programatically called.
    * onUncheckAll - The same as above.
    * onFocus - When the dropdown gains focus.
    * onBlur - When the dropdown is blurred.
    * onOptionGroupCheck - Fires when a an optionGroup label is clicked on.
    * onOptionGroupUnCheck - Fires when a an optionGroup label is clicked off.
    * onSelect - Fires when any checkbox is toggled by the user or programmtically. 
    * onClick - Fires when any checkbox is toggled by the user only.
  * Events that you can expect to see on the masseuse collections `.$select` property.  
    * onOpen - Fires when the dropdown list is opened.
    * onClose - Fires when the dropdown list is closed.
    * onFocus - When the dropdown gains focus.
    * onBlur - When the dropdown is blurred.
  * The masseuse collections `.$select` property will have the following methods:
    * enable - Enables the select element.
    * disable - Disbales the select element.
    * focus - Gives focus to the select element.
    * blur - Blures the select element.
    * refresh - Force reload the select element.
    
## Parent Tag Options
  * collection - object - The masseuse collection you want to bind to. The select will look for the `.models` property automatically.
  * label - string - The property on each model you want to use as the label in the default functionality. If no label is found, it will try to use a property called `label` on your models. If that is not found, you will see console errors.
  * keepOpen - boolean - Force the select to stay open.
  * maxHeight - int/percent - The max height the dropdown will have. Default is 250px.
  * width - int/percent - The forced width the dropdown will have. Defaults to be big enough for the labels.
  * filter - boolean - Whether to show the search box or not. Default is true.
  * position - string - Sets the position of the dropdown. Valid options are 'top' and 'bottom'. Default is 'bottom'.
  * single - boolean - If set to true, only allows the user to select one item.
  * multiple - boolean - Whether or not to show multiple items in a row. Default is false.
  * multipleWidth - int - Show multple items width. Default is '80'.
  * etcaetera - boolean - Add “…” after selected options if minumimCountSelected is set. Overrides countSelected option. Default is false.
  * countSelectedText - false/string - ‘#’ is replaced with the count of selected items, ‘%’ is replaces with total items. Default is '# of % selected'.
  * minumimCountSelected - int - The countSelected option will be shown only if more than X items where selected. Default is 3.
  * allSelectedtext - false/string - The text displays when the select all selected. Default is 'All selected'.
  * selectAllText - string - The 'Select All' text. Default is 'Select All'.
  * showSelectAll - boolean - To show(true) or hide(false) the select all button. Default is shown(true).
  * placeholder - string - The placeholder text. Default is ''.
  * initializeOpen - boolean - To initialize the element with the dropdown open. Default is false.
  



This was forked from, blatantly rips off, and owes 99% of its usefulness to the amazing developers contributing to [the jquery multiple select plugin](http://wenzhixin.net.cn/p/multiple-select).

## Requirements 
  * [Polymer](http://www.polymer-project.org/)
  * [Masseuse](https://github.com/Solid-Interactive/masseuse)

## Installation
  Will use bower, but not yet implemented.
  You will also need to put it in your main.js, details to follow.
  
## Browser Compatability
unkown.

## LICENSE

[The MIT License](https://github.com/wenzhixin/multiple-select/blob/master/LICENSE)
