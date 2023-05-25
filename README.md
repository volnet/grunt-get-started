# Official Grunt Getting Started Document

Source: <https://gruntjs.com/getting-started>

## Steps: How to create a new Grunt project

### 1. Install grunt-cli

> Current Directory: anywhere

```bash
npm install --golbal grunt-cli
```

### 2. Init npm project

1. basic infomation

> Current Directory: grunt-get-started/

```bash
mkdir grunt-get-started
cd grunt-get-started
npm init
```

2. packages

> Current Directory: grunt-get-started/

```bash
npm install --save-dev grunt
npm install --save-dev grunt-contrib-jshint
npm install --save-dev grunt-contrib-nodeunit
npm install --save-dev grunt-contrib-uglify
```

### 3. Config Gruntfile.js

> Current Directory: grunt-get-started/

```bash
touch Gruntfile.js
```

Edit the `Gruntfile.js` file.

```javascript
module.exports = function(grunt) {

  // Project configuration.
  grunt.initConfig({
    pkg: grunt.file.readJSON('package.json'),
    uglify: {
      options: {
        banner: '/*! <%= pkg.name %> <%= grunt.template.today("yyyy-mm-dd") %> */\n'
      },
      build: {
        src: 'src/<%= pkg.name %>.js',
        dest: 'build/<%= pkg.name %>.min.js'
      }
    }
  });

  // Load the plugin that provides the "uglify" task.
  grunt.loadNpmTasks('grunt-contrib-uglify');

  // Default task(s).
  grunt.registerTask('default', ['uglify']);

};
```

### 4. Add example code

> Current Directory: grunt-get-started/

```bash
mkdir src
cd src
touch grunt-get-started.js
```

> Current Directory: grunt-get-started/

Edit the `grunt-get-started.js` file.

```javascript
```

### 5. Run Grunt

> Current Directory: grunt-get-started/

```bash
grunt
```

## Steps: How to run current project

```bash
git clone https://github.com/volnet/grunt-get-started.git
cd grunt-get-started
npm install
grunt
```
