# Pasta `@types` em Next.js com TypeScript

## O que é a pasta `@types`?

A pasta `@types` dentro do diretório `src` em um projeto Next.js é utilizada para armazenar definições de tipos TypeScript personalizadas. Isso é especialmente útil em projetos que utilizam TypeScript, pois permite que você estenda tipos e interfaces de acordo com as necessidades do seu projeto.

### Quando Utilizar a Pasta `@types`?

1. **Extensão de Tipos**: Quando você precisa estender os tipos de uma biblioteca externa para incluir funcionalidades adicionais ou adaptar a tipagem às necessidades do seu projeto.

2. **Definições de Tipos Personalizadas**: Se você estiver criando funções ou componentes personalizados e precisar definir tipos específicos para eles, a pasta `@types` é o lugar ideal para organizar essas definições.

3. **Suporte para Bibliotecas sem Tipagem**: Em alguns casos, bibliotecas externas podem não fornecer definições de tipos, ou as definições existentes podem não cobrir todas as funcionalidades que você está usando. Nesses casos, você pode criar suas próprias definições na pasta `@types`.

## Exemplo: Extensão do `styled-components` para um Tema Personalizado

Um uso comum da pasta `@types` é estender as definições de tipos para bibliotecas como o `styled-components`. Aqui está como você pode fazer isso para adicionar um tema personalizado ao seu projeto.

### 1. Criar a Estrutura de Diretórios

No seu projeto, crie a seguinte estrutura de diretórios:

```bash
src
└── @types
    └── styled.d.ts
```

### 2. Definir o Tema Personalizado

No arquivo `styled.d.ts`, você pode definir o tema personalizado da seguinte forma:

```typescript
// src/@types/styled.d.ts

import 'styled-components';

declare module 'styled-components' {
  export interface DefaultTheme {
    colors: {
      primary: string;
      secondary: string;
      background: string;
      text: string;
    };
    spacing: {
      small: string;
      medium: string;
      large: string;
    };
  }
}
```

### 3. Usar o Tema no Projeto

Depois de definir o tema, você pode usá-lo em todo o seu projeto Next.js. No arquivo onde você define o tema, ele pode ser usado assim:

```typescript
// src/theme.ts

import { DefaultTheme } from 'styled-components';

export const theme: DefaultTheme = {
  colors: {
    primary: '#0070f3',
    secondary: '#1a1a1a',
    background: '#f5f5f5',
    text: '#333333',
  },
  spacing: {
    small: '8px',
    medium: '16px',
    large: '24px',
  },
};
```

E para aplicar o tema:

```typescript
// src/pages/_app.tsx

import { ThemeProvider } from 'styled-components';
import { theme } from '../theme';

function MyApp({ Component, pageProps }) {
  return (
    <ThemeProvider theme={theme}>
      <Component {...pageProps} />
    </ThemeProvider>
  );
}

export default MyApp;
```

### Conclusão

A pasta `@types` é essencial para organizar e manter as definições de tipos TypeScript em um projeto Next.js, especialmente quando você está trabalhando com bibliotecas externas como o `styled-components`. Ao utilizar essa pasta, você pode personalizar e estender facilmente a tipagem de seu projeto para atender a necessidades específicas.
