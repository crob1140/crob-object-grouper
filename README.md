# \<crob-object-grouper\>


```<crob-object-grouper>```  is a utility component that can used to group objects into groups defined by a property value. As a hybrid component, it is compatible with both Polymer 1.x and 2.x projects.

This component ensures that any changes to the properties of an object in either the 'items' property or the group
will also fire a change notification for the corresponding path in the other property.

## Usage
To use this component, simply set the **items** and **groupBy** properties of the ```crob-object-grouper``` and extract the resulting values from the **groups** property.

```html
<crob-object-grouper
    items="[[items]]"
    group-by="[[groupBy]]"
    groups="{{groups}}"
    group-names="{{groupNames}}">
</crob-object-grouper>
```

The **items** property is an array of objects, which each have a property value defining which group it should belong in.

The **groupBy** property specifies the name of the property that should be used to determine which group each item belongs to.

The resulting **groups** property is a dictionary mapping each **groupBy** property value to the subset of objects in the **items** property that are using this value. For example, if each object in **items** has a property called 'colour', some of which are using the value 'Red' and others using the value 'Green', then the resulting keys in the **groups** property will be 'Red' and 'Green'.

The **groupNames** property provides the keys of the **groups** property that have a non-empty corresponding value list. This can be used to iterate over all of the groups, as it will update when groups are added and/or removed as a result of item changes.