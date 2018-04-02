# Installation

- [Installation](#installation)
    - [Using Atom/VSCode](#using-atom-vscode)
    - [Using Arduino IDE](#using-arduino-ide)
- [Supported Boards](#supported-boards)
- [License](#license)

<a name="installation"></a>
## Installation

> {tip}It's highly recommended to avoid using Arduino IDE, instead, use [`Atom`](https://atom.io/) or [`VSCode`](https://code.visualstudio.com/) text-editor with [`Platform IO`](http://platformio.org/platformio-ide) for a better development environment.

<a name="using-atom-vscode"></a>
### Using Atom/VSCode

If you are using Atom/VSCode with Platform IO you have two ways

**First way** (recommended ✌️)

    pio lib install zino
    
**Second way**

Create a new project then [Download the library](https://github.com/saleem-hadad/zino/archive/master.zip) and extract the files into the ```lib``` folder.


<a name="using-arduino-ide"></a>
### Using Arduino IDE

> {note}I did NOT test the library on the Arduino IDE, so please notify me if you get any warning/error!

1. [Download the library](https://github.com/saleem-hadad/zino/archive/master.zip)
2. navigate to Arduino IDE > click on ```sketch``` > ```include Library``` > add .Zip library then add the ```zino-master.zip```

<a name="supported-boards"></a>
## Supported Boards

+ ### UNO

<a name="license"></a>
## License

This library is licensed under the MIT License - see the [LICENSE.md](https://github.com/saleem-hadad/zino/blob/master/LICENSE) file for details.