# react-avatar
👤 Load, crop and preview avatar with ReactJS component 

[![npm version](https://badge.fury.io/js/react-avatar-edit.svg)](https://badge.fury.io/js/react-avatar-edit)

## Demo

![](https://media.giphy.com/media/3o7aD1fCeJxzNu2uYg/giphy.gif)

## [Demo website](https://kirill3333.github.io/react-avatar/)

## Usage

```javascript
import React from 'react'
import ReactDOM from 'react-dom'
import Avatar from 'react-avatar-edit'

class App extends React.Component {

  constructor(props) {
    super(props)
    const src = './example/einshtein.jpg'
    this.state = {
      preview: null,
      src
    }
    this.onCrop = this.onCrop.bind(this)
    this.onClose = this.onClose.bind(this)
  }
  
  onClose() {
    this.setState({preview: null})
  }
  
  onCrop(preview) {
    this.setState({preview})
  }
  
  render () {
    return (
      <div>
        <Avatar
          width={390}
          height={295}
          onCrop={this.onCrop}
          onClose={this.onClose}
          src={this.state.src}
        />
        <img src={this.state.preview} alt="Preview" />
      </div>
    )
  }
}

ReactDOM.render(<App /> , document.getElementById('root'))
```

## Component properties

| Prop                   | Type             | Description
| ---------------------- | ---------------- | ---------------
| img                    | Image            | The Image object to display
| src                    | String/Base64    | The url ot base64 string to load (use urls from your domain to prevent security errors)
| width                  | Number           | The width of the editor
| height                 | Number           | The height of the editor (image will fit to this height)
| cropRadius             | Number           | The crop area radius in px (default: 100)
| cropColor              | String           | The crop border color (default: white)
| lineWidth              | Number           | The crop border width (default: 4)
| minCropRadius          | Number           | The min crop area radius in px (default: 30)
| backgroundColor        | Sting            | The color of the image background (default: white)
| closeIconColor         | String           | The close button color (default: white)
| shadingColor           | String           | The shading color (default: grey)
| shadingOpacity         | Number           | The shading area opacity (default: 0.6)
| mimeTypes              | String           | The mime types used to filter loaded files (default: image/jpeg,image/png)
| onImageLoad(image)     | Function         | Invoked when image based on src prop finish loading
| onCrop(image)          | Function         | Invoked when user drag&drop event stop and return croped image in base64 sting
| onFileLoad(file)       | Function         | Invoked when user upload file with internal file loader
| onClose()              | Function         | Invoked when user clock on close editor button

## Contributing

* To start developer server please use ```npm run start```
* To build production bundle use ```npm run build```
