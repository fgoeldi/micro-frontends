

# Microfrontend POC

This is a proof of concept for a microfrontend architecture with two applications: **Host** and **Remote**. The **Host** application consumes a component exposed by the **Remote** application. Any changes made in the **Remote** application will be reflected in the **Host** application in real-time.

## Project Structure

```
micro-frontends/
│
├── host/          # Host application
│   ├── src/
│   ├──   └── App.tsx
│   ├── webpack.config.js
│   ├── package.json
│   └── ...
│
└── remote/        # Remote application
    ├── src/
    │     └── Hello.tsx
    ├── webpack.config.js
    ├── package.json
    └── ...
```

## Getting Started

To run the microfrontend POC, you need to start both the **Host** and **Remote** applications. Below are the steps to set them up.

### Host Application

1. Navigate to the **Host** directory:
   ```bash
   cd host
   ```

2. Install the dependencies:
   ```bash
   npm install
   ```

3. Start the application:
   ```bash
   npm start
   ```

   The **Host** application will be running on [http://localhost:8080](http://localhost:8080).

### Remote Application

1. Navigate to the **Remote** directory:
   ```bash
   cd remote
   ```

2. Install the dependencies:
   ```bash
   npm install
   ```

3. Start the application:
   ```bash
   npm start
   ```

   The **Remote** application will be running on [http://localhost:3000](http://localhost:3000).

## Overview

- The **Remote** application exposes a `Hello` page that is used by the **Host** application.
- The **Host** application dynamically imports the `Hello` component from the **Remote** application.
- Changes made in the **Remote** application are reflected in the **Host** application in real-time.

### Remote Entry

- When you run the **Remote** application, it generates a `remoteEntry.js` file available at [http://localhost:3000/remoteEntry.js](http://localhost:3000/remoteEntry.js).
- This entry file contains a manifest of all the exposed modules as configured in the `webpack.config.js` of the **Remote** application.

### Live Reload

- The system is configured to support live reloading. Any changes made to the **Remote** application will be immediately visible in the **Host** application without requiring a page refresh.

## Additional Notes

- Ensure that both applications are running simultaneously for the microfrontend setup to work as expected.
- The configuration for module federation, including the exposed modules, can be found in the `webpack.config.js` file of each application.
- For any changes in the **Remote** application’s exposed modules, restart both applications to reflect the updates.

---
