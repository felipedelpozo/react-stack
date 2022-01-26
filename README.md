# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `yarn start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `yarn test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `yarn build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `yarn eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Configuration

### Environment variables

You will find a `.env` file at the root of your project. By default it comes configured:

- For not opening a browser window automatically when running the development server;
- For not generating source maps when generating a production build.

You can change this configuration directly in the file and you can find the full list of supported variables on [Create React App's docs](https://create-react-app.dev/docs/advanced-configuration/).

### Scripts for generating Self Signed Certificates

After creating your project you will find a `ssl` folder containing a shell script. You can use it to generate a self signed certificate to run your development server with `https`.

To do that, run the `scripts/ssl/generate_development_certificate.sh` script. You can even run it in Windows if you have [WSL](https://docs.microsoft.com/en-us/windows/wsl/about) enabled.

The script will generate two files in the `ssl` folder: `development_certificate.key` and `development_certificate.crt`.

**You should NOT commit the generated `.key` and `.crt` files in your repository**. In fact, `.gitignore` is already set up to ignore them (assuming they are in the `ssl` folder). In a shared project, every developer should generate their own self signed certificates. And if you have multiple projects using `https` in development you might wanna consider using a single certificate for all of your projects.

Assuming you ran the shell script, you can start the development server with `https` by adding the following lines in the `.env` file at the root directory of your project:

    SSL_CRT_FILE=ssl/development_certificate.crt
    SSL_KEY_FILE=ssl/development_certificate.key

You also need to install the self signed certificates in your operating system in the Trusted Root folder. Otherwise your browser will show an error when you try to run the app.

With that, the next time you [run your development server](#npm-start-or-yarn-start), it will use `https` and you will be able to access the app at `https://localhost:3000/` (you won't be able to use the `http` URL unless you disable `https` in your `.env` file).

If you are not interested in using `https` in your development server, you can safely delete the `ssl` folder after creating the project.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).
