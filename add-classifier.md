# Add Classifiers

Classifiers control what you can select in a Reality Model.  We will use a classifier to let us select individual buildings.

To use a classifier it must first be found and then once found it must be applied to the Viewport (the window with the 3d view)

## Step 1 - Copy the updated source code

Copy the updated `providers\RealityDataApi.ts` file into your project.  This file has been updated to add two functions, `getAvailableCLassifierListForViewport` that finds the classifiers for this iModel and `setRealityDataClassifier` which applies a classifier to the Viewport.

## Step 2 - Save the classifier into the state

Add the state variable to store the classifier using the following line:

```typescript
  const [classifier, setClassifier] = React.useState<string>("");
```

We want to set the classifier in state during initialization of the Widget.  Find the method called `asyncInitialize` in `MyFirstWidget.tsx`.

Inside the check for the viewport `if (viewport) { ... }` add the following code

```typescript
        const classifiers = await RealityDataApi.getAvailableClassifierListForViewport(viewport);
        if(classifiers) {
          setClassifier(classifiers[0].value);
        }
```

> Hint: Add this code right below the line `setRealityModelList(realityModels);`

## Step 3 - Set the classifier in the viewport

We want to set the classifier when the 3d reality model is turned on.  Find the function called when we toggle the button is pressed and add the following line:

```typescript
          RealityDataApi.setRealityDataClassifier(viewport, classifier);
```

## Step 4 - Test

Make sure the all the modified files are saved and use the command `npm run start` to rebuild and start the application.

## Change The Hilite color

By default the color is light blue but that can be changed by changing the hilite settings on the viewport like this:

```typescript
    if (viewport) {
      viewport.hilite = {...viewport.hilite, color: newColor};
    }
```

> Note: we will use this code later

This creates a new copy of the existing hilite settings replacing the previous color with the `newColor`.

To do this we need to store the current color in the state, provide a way to select a new color and a function that updates the state and viewport.

For the state we will store a variable of type `ColorDef` like this:

```typescript
  const [hiliteColor, setHiliteColor] = React.useState<ColorDef>(ColorDef.green);
```

When the widget is initialized add code to save default hilite color in state:

```typescript
        setHiliteColor(viewport.hilite.color);
```

Next add a `ColorPickerButton` after the `ToggleSwitch` to select the new color:

```typescript
      <ColorPickerButton initialColor={hiliteColor} onColorPick={onColorChange} />
```

Finally create a function called `onColorChange` that sets the hilite color state and updates the hilite settings on the viewport.  Both bits of code can be found above.  

Here is an empty version of the onColorChange method to start with:

```typescript
  const onColorChange = async (newColor: ColorDef) => {
    // Code goes here
  }
```