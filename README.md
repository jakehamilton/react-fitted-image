# react-fitted-image

Pictures are always difficult to handle in web page, especially in a responsive way. A well-known workaround is to style the <img /> with something like this:
```css
img {
  max-width: 100%;
  height: auto;
}
```

This method works well, but there is a lot of cases where it's not sufficient. Fortunately CSS introduced some times ago the ["object-fit" property](https://developer.mozilla.org/fr/docs/Web/CSS/object-fit), improving the way we can handle image displaying.
The current component provides an easy react binding to display images with object-fit property.

In addition, you can provide a loader which will be displayed during the image processing by the browser.

Object-fit is well supported by browsers but not all of them for now ( see [Caniuse](http://caniuse.com/#feat=object-fit) ). To work on stuffs like IE, a basic test is done with [CSS.supports](https://developer.mozilla.org/en/docs/Web/API/CSS/supports) to provide a fallback based on "background" CSS property.

## Usage

### Install
```
npm install --save react-fitted-image
```

### Properties
|    Property    | Type |          Description          | Default value | Required |
| -------------  | ---- |          -----------          | ------------- | -------- |
| background     | bool | Force the component to use the CSS bacground properties | false | no |
| className      | string | Custom classname for the component | _ | no |
| fit            | string | Value of the object-fit property. Can be "auto", "contain", or "cover" | "auto" | no |
| loader         | element | Component to use as loader | _ | no |
| src            | string | Image url to render | _ | yes |
| style          | object | Custom styles | {} | no |

### Example
```javascript
<FittedImage
  fit="contain"
  loader={<div>Loading</div>}
  src="public/img.jpg" />
```

You'll also have to include the CSS or SCSS file in your project.
See example for more details.

## Development
Clone the repository:
```
git clone https://github.com/the-cormoran/react-fitted-image.git
```
Install dependencies:
```
cd react-fitted-image && npm install
```
Commands:
```shell
npm run build 	# build the lib to publish the package
npm run example # build the example
npm run test	  # run the tests
npm run lint    # lint the code
```