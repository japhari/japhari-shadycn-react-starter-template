# Vite + React + Tailwind Project Setup

## Setup Steps

1. First, run the create command:

```bash
npm create vite@latest
```

2. You'll see these prompts:

```bash
npx
create-vite

│
◇ Project name:
│ vite-react-project
│
◇ Select a framework:
│ React
│
◇ Select a variant:
│ JavaScript
│
◇ Scaffolding project in
```

3. Navigate to the project directory:

```bash
cd vite-react-project
```

4. Install dependencies:

```bash
npm install
```

5. Install Tailwind CSS and its Vite plugin:

```bash
npm install tailwindcss @tailwindcss/vite
```

6. Configure the Vite plugin:

   - Add the @tailwindcss/vite plugin to your Vite configuration in `vite.config.js`:

   ```js
   import { defineConfig } from "vite";
   import react from "@vitejs/plugin-react";
   import tailwind from "@tailwindcss/vite";

   export default defineConfig({
     plugins: [react(), tailwind()],
   });
   ```

7. Import Tailwind CSS:

   - Add the following import to your main CSS file (`src/index.css`):

   ```css
   @import "tailwindcss";
   ```

8. Start the development server:

```bash
npm run dev
```

9. Start using Tailwind:
   - Make sure your compiled CSS is included in the `<head>` of your HTML
   - Begin using Tailwind's utility classes in your components

The development server will start at `http://localhost:5173/`

## Project Structure

```
vite-react-project/
├── public/
│   └── vite.svg
├── src/
│   ├── assets/
│   │   └── react.svg
│   ├── App.css
│   ├── App.jsx
│   ├── index.css
│   └── main.jsx
├── index.html
├── package.json
└── vite.config.js
```

## Available Scripts

- `npm run dev` - Starts the development server
- `npm run build` - Builds the app for production
- `npm run preview` - Locally preview the production build

## Learn More

- [Vite Documentation](https://vitejs.dev/)
- [React Documentation](https://react.dev/)
- [Tailwind CSS Documentation](https://tailwindcss.com/)

## ShadCN Configuration

To integrate ShadCN components into this project, follow these steps:

1. **Install ShadCN CLI**:

   ```bash
   npx shadcn@latest init
   ```

2. **Validate Configuration**:
   Ensure that your `tsconfig.json` file includes the following alias:

   ```json
   {
     "compilerOptions": {
       "baseUrl": "./",
       "paths": {
         "@/*": ["src/*"]
       }
     }
   }
   ```

3. **Update Vite Config**:
   Add the alias configuration to `vite.config.js`:

   ```js
   import { defineConfig } from "vite";
   import react from "@vitejs/plugin-react";
   import path from "path";

   export default defineConfig({
     plugins: [react()],
     resolve: {
       alias: {
         "@": path.resolve(__dirname, "./src"),
       },
     },
   });
   ```

4. **Start Using ShadCN Components**:
   Import and use components like `Button` in your project:

   ```tsx
   import { Button } from "@/components/ui/button";

   function Example() {
     return <Button variant='default'>Click Me</Button>;
   }
   ```

5. **Learn More**:
   Visit the [ShadCN Documentation](https://ui.shadcn.com/docs) for more details.

## Try ShadCN Button Component

To add and use the ShadCN `Button` component in your project, follow these steps:

1. **Add the Button Component**:

   Run the following command to add the `Button` component:

   ```bash
   npx shadcn@latest add button
   ```

2. **Use the Button Component in `App.jsx`**:

   Update your `App.jsx` file to use the ShadCN `Button` component. Here’s an example:

   ```jsx
   import { Button } from "@/components/ui/button";

   function App() {
     const [count, setCount] = useState(0);

     return (
       <div>
         <h1 className='text-3xl font-bold'>ShadCN Button Example</h1>
         <Button onClick={() => setCount((count) => count + 1)}>
           Count is {count}
         </Button>
       </div>
     );
   }

   export default App;
   ```

3. **Start the Development Server**:

   Run the following command to start the development server and see the button in action:

   ```bash
   npm run dev
   ```

## Workspace Structure

Here is a screenshot of the workspace structure:

![Workspace Structure](../Screenshot%202025-06-10%20at%2017.38.04.png)
