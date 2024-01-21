# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default {
  // other rules...
  parserOptions: {
    ecmaVersion: "latest",
    sourceType: "module",
    project: ["./tsconfig.json", "./tsconfig.node.json"],
    tsconfigRootDir: __dirname,
  },
};
```

- Replace `plugin:@typescript-eslint/recommended` to `plugin:@typescript-eslint/recommended-type-checked` or `plugin:@typescript-eslint/strict-type-checked`
- Optionally add `plugin:@typescript-eslint/stylistic-type-checked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and add `plugin:react/recommended` & `plugin:react/jsx-runtime` to the `extends` list

1 - npm create vite@latest ./ (y -- react )
2 - npm install
3 - src main.tsx
4 - src App.tsx
5 - src global.css
6 - npm install -D tailwindcss postcss autoprefixer
7 - npx tailwindcss init -p
8 - https://tailwindcss.com/docs/guides/vite
9 - src \_auth forms RootLayout.tsx Signinform.tsx Signform.tsx
10 - src \_auth AuthLayout.tsx
11 - src \_root pages Home.tsx
12 - https://ui.shadcn.com/docs/installation/vite
tsconfig.json icerisine ("baseUrl": ".",
"paths": {
"@/_": [
"./src/_"
]
})
13 - npm i -D @types/node
14 - vite.config.ts (import path from "path"
import react from "@vitejs/plugin-react"
import { defineConfig } from "vite"

      export default defineConfig({
        plugins: [react()],
        resolve: {
          alias: {
            "@": path.resolve(__dirname, "./src"),
          },
        },
      })
      )

15 - npx shadcn-ui@latest init  
16 - (y yes default slate src/global.css yes enter enter enter yes y)
17 - npx shadcn-ui@latest add button (components\ui button.tsx olustu)
18 - npx shadcn-ui@latest add form (form olusturulmak icin kullandi) (components/ui form.tsx label.tsx olustu)
19 - SignupForm.tsx ("use client"
import \* as z from "zod"
const formSchema = z.object({
username: z.string().min(2).max(50),
})
)
20 - SignupForm.tsx (import {
Form,
FormControl,
FormDescription,
FormField,
FormItem,
FormLabel,
FormMessage,
} from "@/components/ui/form"
// 1. Define your form.
const form = useForm<z.infer<typeof formSchema>>({
resolver: zodResolver(formSchema),
defaultValues: {
username: "",
},
})

// 2. Define a submit handler.
function onSubmit(values: z.infer<typeof formSchema>) {
// Do something with the form values.
// ✅ This will be type-safe and validated.
console.log(values)
})
21 - npx shadcn-ui@latest add input
22 - appwrite'da uygulama olusturuldu. lib appwrite config.ts olusturuldu.
23 - npm install appwrite
24 - lib appwrite app.ts olusturuldu.
25 - types index.ts olusturuldu.
26 - appwrite storage create bucket 'media' olusturuldu.
27 - apppwrite databases createcollection -- db olusturuldu.
28 - appwrite databases createcollection 'posts', 'Saves' ve 'users' olusturuldu
29 - appwrite databases setting permissions 'create read update delete' secildi.
30 - appwrite databases posts attributes createattribute --> Relationship --> two way relationship --> related collection users --> attribute key creator --> relation many to one --> on deleteing a document Set NULL ----> Kimin gonderdigini gormek icin
31 - appwrite databases posts attributes createattribute --> Relationship --> two way relationship --> related collection: users --> attribute key: likes --> attribute key(r.c.): liked --> relation: many to many --> on deleteing a document Set NULL ----> Postlari begenmek
31 - appwrite databases posts attributes createattribute --> String --> Attribute key: caption --> size: 2200
32 - appwrite databases posts attributes createattribute --> String --> Attribute key: tags --> size: 2200 --> array sec
33 - appwrite databases posts attributes createattribute --> URL --> Attribute key: imageUrl --> required sec
34 - appwrite databases posts attributes createattribute --> String --> Attribute key: imageId --> size: 2200 --> required sec
35 - appwrite databases posts attributes createattribute --> String --> Attribute key: location --> size: 2200
36 - appwrite databases posts indexes createindex --> index key: caption --> index type: fulltext --> attribute: caption --> order: desc
37 - appwrite databases users attributes createattribute --> String --> Attribute key: name --> size: 2200
38 - appwrite databases users attributes createattribute --> String --> Attribute key: username --> size: 2200
39 - appwrite databases users attributes createattribute --> String --> Attribute key: accountId --> size: 2200 --> --> required sec
40 - appwrite databases users attributes createattribute --> email --> Attribute key: email
41 - appwrite databases users attributes createattribute --> String --> Attribute key: bio --> size: 2200
42 - appwrite databases users attributes createattribute --> String --> Attribute key: imageId --> size: 2200
43 - appwrite databases users attributes createattribute --> url --> Attribute key: imageUrl --> required
44 - appwrite databases saves attributes createattribute --> Relationship --> two way relationship --> related collection: users --> attribute key: user --> attribute key(r.c.): save --> relation: many to one --> on deleteing a document Set NULL  
45 - appwrite databases saves attributes createattribute --> Relationship --> two way relationship --> related collection: posts --> attribute key: post --> attribute key(r.c.): save --> relation: many to one --> on deleteing a document Set NULL
46 - config.ts'de .env'deki sifreler import edildi
47 - api.ts
48 - https://ui.shadcn.com/docs/components/toast --> npx shadcn-ui@latest add toast --> components ui toast.tsx, toaster.tsx, use-toasts.tsx dosyalari olustu.
49 - https://tanstack.com/query/latest
50 - lib react-query queriesAndMutations.ts olusturuldu
51 - npm i @tanstack/react-query
52 - lib react-query QueryProvider.tsx olusturuldu.
53 - components shared Topbar.tsx, bottombar.tsx ve leftsidebar.tsx olusturuldu.
54 - constants index.ts olusturuldu.
55 - pages allusers.tsx olusturuldu.
56 - components forms PostForm.tsx olusturuldu. Icerigi https://ui.shadcn.com/docs/components/form buradan olusturuldu.
57 - components shared fileuploader.tsx olusturuldu.
58 - npm install react-dropzone
59 - fileuploader.jsx dosyasinin icerisine 'https://react-dropzone.js.org/' buradaki icerikler yerlestirildi.
60 - appwrite storage settings permissions any "create read update delete" izin verildi.












