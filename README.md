
# **Invite-Friends-App Documentation**

## **Overview**

This is a Vue 3 application built with TypeScript, SCSS, and Vite. The app includes a friend invitation feature with components for buttons, lists, and layout.

---

## **Project Structure**

```
invite-friends-app/
│
├── public/                     # Static assets
├── src/                        # Source code
│   ├── assets/                 # Images, fonts, etc.
│   │   ├── fonts/              # Font files
│   │   └── images/             # Images used in the app
│   ├── components/             # Vue components
│   │   ├── AppButton.vue       # Button component
│   │   ├── AppList.vue         # Friends list component
│   │   ├── AppMain.vue         # Main content component
│   │   ├── AppTitle.vue        # Title component
│   │   └── FriendsList.vue     # Friends list page
│   ├── styles/                 # SCSS files
│   │   ├── fonts.scss          # Fonts configuration
│   │   └── variables.scss      # SCSS variables
│   ├── App.vue                 # Root Vue component
│   ├── main.ts                 # Entry point
│   ├── shims-vue.d.ts          # TypeScript shim for .vue files
│   ├── style.css               # Global styles
│   └── vite-env.d.ts           # Environment types
├── .gitignore                  # Files to ignore in git
├── index.html                  # Entry HTML file
├── package.json                # Project metadata and dependencies
├── tsconfig.json               # TypeScript configuration
├── tsconfig.app.json           # App-specific TypeScript config
├── tsconfig.node.json          # Node-specific TypeScript config
└── vite.config.ts              # Vite configuration
```

---

## **Installation**

To run this project locally, follow these steps:

1. **Clone the repository**:

   ```bash
   git clone <repository-url>
   cd invite-friends-app
   ```
2. **Install dependencies**:

   ```bash
   npm install
   ```

   or

   ```bash
   yarn install
   ```

---

## **Running the Development Server**

Start the Vite development server:

```bash
npm run dev
```

or

```bash
yarn dev
```

The app will be available at `http://localhost:5173`.

---

## **Building for Production**

To create an optimized production build:

```bash
npm run build
```

or

```bash
yarn build
```

This will generate a `dist/` folder with the production-ready files.

---

## **Preview Production Build**

To locally preview the production build:

```bash
npm run preview
```

or

```bash
yarn preview
```

---

## **Deployment**

### Deploy to Static Hosting Services

You can deploy the generated `dist/` folder to any static hosting service, such as:

- **Vercel**
- **Netlify**
- **GitHub Pages**

#### Example Deployment with Vercel:

1. Install Vercel CLI:
   ```bash
   npm install -g vercel
   ```
2. Deploy the project:
   ```bash
   vercel
   ```
3. Follow the prompts to complete deployment.

---

## **SCSS and Styling**

- **Global variables** are defined in `src/styles/variables.scss`.
- **Fonts** are imported in `src/styles/fonts.scss`.

To include global styles in your components, import them as follows:

```scss
@use '@/styles/variables.scss' as *;
```

---

## **Scripts**

- `npm run dev`: Starts the development server.
- `npm run build`: Builds the project for production.
- `npm run preview`: Previews the production build.
- `npm run lint`: Lints the code.

---

## **Environment Variables**

To use environment variables, create a `.env` file in the root directory:

```env
VITE_API_URL=https://api.example.com
```

Access the variable in the app:

```ts
const apiUrl = import.meta.env.VITE_API_URL;
```

---

## **TypeScript Configuration**

The project uses TypeScript for type safety and better developer experience. Key configurations:

- `tsconfig.json`: Base TypeScript configuration.
- `tsconfig.app.json`: For application files.
- `tsconfig.node.json`: For Node-specific configurations.

---

## **Contributing**

1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature/your-feature
   ```
3. Make your changes and commit them:
   ```bash
   git commit -m "Add your feature"
   ```
4. Push to the branch:
   ```bash
   git push origin feature/your-feature
   ```
5. Open a Pull Request.

---

## **License**

This project is licensed under the MIT License.

---

## **Contact**

For any questions or suggestions, feel free to contact:

- **Email**: [anton-vorobiov-devl@gmail.com]
- **GitHub**: [https://github.com/anton-vorobiov-dev]

---

Happy coding! 🚀
