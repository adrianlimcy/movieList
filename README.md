# Steps
1. mkdir movieList
2. cd movieList
3. npm init -y
4. npm install --save-dev webpack webpack-cli
5. add start and build lines in package.json
    "start": "webpack --mode development",
    "build": "webpack --mode production",
6. mkdir src
7. cd src
8. touch index.js
9. add code into index.js
    console.log("movieList")
10. cd ../
11. npm start
12. npm dist/main.js
13. npm install react react-dom
14. npm install --save-dev @babel/core @babel/preset-env @babel/preset-react babel-loader
15. touch webpack.config.js
    module.exports = {
        module: {
            rules: [
                {
                    test: /\.js$/,
                    exclude: /node_modules/,
                    use: {
                        loader:'babel-loader',
                    },
                },
            ],
        },
    }
16. touch .babelrc
    {
        "presets": [
            [
                "@babel/preset-env",
                {
                    "targets": {
                        "node": "current"
                    }
                }
            ],
            "@babel/react"
        ]
    }
17. update src/index.js file with code
18. touch index.html in src folder and fill in code
19. npm install --save-dev html-webpack-plugin
20. add in new lines in webpack.config.js
    const HtmlWebPackPlugin = require('html-webpack-plugin');

    const htmlPlugin = new HtmlWebPackPlugin({
        template: './src/index.html',
        filename: './index.html'
    })

    module.exports = {
        module: {
            rules: [
                {
                    test: /\.js$/,
                    exclude: /node_modules/,
                    use: {
                        loader:'babel-loader',
                    },
                },
            ],
        },
        plugins: [htmlPlugin]
    }
21. npm start