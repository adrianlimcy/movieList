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
22. npm install --save-dev webpack-dev-server\
23. add line into package.json
    "start": "webpack-dev-server --mode development --open",
24. npm start
    - server is live
    - can be seen on localhost:8080
25. mkdir src/containers
26. cd src/containers
27. touch List.js
28. add code into List.js
29. amend index.js in src/index.js
30. mkdir src/components/Card
31. touch src/components/Card/Card.js
32. add in code for Card.js
33. amend code for List.js
34. mkdir assets
35. touch assets/data.json
36. copy assets and media from tutorial github page
37. amend code for Card.js
38. add constructor in List.js
39. add async/await code in List.js to retrieve data
40. npm install --save-dev bootstrap
41. add code into index.js
    import 'bootstrap/dist/css/bootstrap.min.css';
42. npm install --save-dev css-loader style-loader
43. add code into webpack.config.js
    {
        test: /\.css$/,
        use: ['style-loader', 'css-loader']
    }
44. add bootstrap styling css into index.js
45. add bootstrap styling css into List.js
46. add bootstrap styling css into Card.js
47. touch up css in index.js
48. npm install --save-dev eslint eslint-loader eslint-plugin-react
49. touch .eslintrc.js
50. add eslint-loader into webpack.config.js
51. npm install --save prop-types
52. 