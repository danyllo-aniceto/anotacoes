# Projeto Next.js com Husky

Este repositório contém um projeto desenvolvido com [Next.js](https://nextjs.org/), um framework React poderoso e flexível para a construção de aplicações web. Além disso, utilizamos o [Husky](https://typicode.github.io/husky/#/) para garantir a qualidade do código através da automatização de tarefas usando *Git hooks*.

## Sumário

- [O que é Next.js?](#o-que-é-nextjs)
- [Principais Recursos do Next.js](#principais-recursos-do-nextjs)
- [Configuração do Husky](#configuração-do-husky)
- [Scripts Disponíveis](#scripts-disponíveis)
- [Como Contribuir](#como-contribuir)
- [Licença](#licença)

## O que é Next.js?

Next.js é um framework de React para a construção de aplicações web modernas, que oferece recursos como renderização do lado do servidor (SSR), geração de sites estáticos (SSG), roteamento simplificado, e muito mais. Ele é amplamente utilizado por desenvolvedores que desejam criar aplicações de alto desempenho, escaláveis e otimizadas para SEO.

### Principais Recursos do Next.js

- **Renderização Híbrida:** Suporte tanto para Server-Side Rendering (SSR) quanto para Static Site Generation (SSG).
- **Roteamento Automático:** Páginas são automaticamente mapeadas para URLs baseadas na estrutura de arquivos dentro da pasta `pages`.
- **Suporte a API Routes:** Permite criar rapidamente APIs RESTful com Node.js diretamente no projeto Next.js.
- **Otimização de Imagens:** Otimiza automaticamente as imagens para melhorar o desempenho.
- **Suporte a CSS e Sass:** Inclui suporte embutido para CSS, Sass, e CSS-in-JS (styled-components).
- **Deploy Simples:** Integração direta com plataformas como Vercel, facilitando o deploy e a hospedagem.

## Renderização Client-Side e Server-Side

Next.js oferece suporte tanto para **Client-Side Rendering (CSR)** quanto para **Server-Side Rendering (SSR)**, permitindo que você escolha a abordagem mais adequada para cada parte de sua aplicação. Abaixo, explicamos o que são essas técnicas e por que elas são importantes.

### Client-Side Rendering (CSR)

**Client-Side Rendering** é o processo em que a renderização da aplicação é feita no navegador do usuário. O servidor envia ao cliente (navegador) um arquivo HTML básico junto com os arquivos JavaScript necessários. Esses arquivos JavaScript então constroem e exibem o conteúdo da página no navegador.

#### Vantagens do CSR:

- **Interatividade Rápida:** Como o HTML inicial é leve, ele é carregado rapidamente. Depois que o JavaScript é carregado e executado, a aplicação se torna interativa.
- **Recursos Dinâmicos:** A renderização no cliente permite a construção de interfaces ricas e dinâmicas, onde o conteúdo pode ser atualizado sem a necessidade de recarregar a página inteira.
- **Menos Carga no Servidor:** Como a renderização ocorre no lado do cliente, o servidor não precisa processar a lógica de renderização, reduzindo sua carga.

#### Desvantagens do CSR:

- **SEO Limitado:** Os motores de busca podem ter dificuldade em indexar o conteúdo, pois ele não está presente no HTML inicial.
- **Maior Tempo de Interatividade (TTI):** A aplicação pode demorar mais para ser totalmente interativa, pois depende do carregamento e execução do JavaScript.

### Server-Side Rendering (SSR)

**Server-Side Rendering** é o processo em que o servidor gera o HTML completo para cada página e o envia ao cliente. O navegador do usuário recebe o HTML pronto, o que significa que o conteúdo da página é visível imediatamente, antes que o JavaScript seja carregado e executado.

#### Vantagens do SSR:

- **Melhor SEO:** Como o HTML completo é entregue ao navegador, os motores de busca podem indexar o conteúdo de maneira eficaz.
- **Renderização Inicial Rápida:** O usuário vê o conteúdo da página imediatamente, melhorando a experiência em termos de percepção de desempenho.
- **Suporte a Dispositivos Lentos:** Dispositivos com menor capacidade de processamento podem beneficiar-se de SSR, já que não precisam renderizar o conteúdo client-side.

#### Desvantagens do SSR:

- **Maior Carga no Servidor:** O servidor precisa processar a lógica de renderização para cada requisição, o que pode aumentar a carga, especialmente em aplicações de grande escala.
- **Interatividade Atrasada:** Embora o conteúdo seja visível imediatamente, a interatividade (via JavaScript) pode ter um pequeno atraso enquanto o JavaScript é carregado e executado.

### Por que isso é importante?

Escolher entre CSR e SSR pode impactar significativamente o desempenho, SEO, e a experiência do usuário de sua aplicação. Em muitos casos, é vantajoso combinar ambas as abordagens para aproveitar o melhor dos dois mundos. Por exemplo, você pode usar SSR para páginas onde o SEO é crucial e CSR para partes da aplicação que exigem alta interatividade.

### Como o Next.js facilita isso?

Next.js facilita o uso de SSR, CSR e até mesmo **Static Site Generation (SSG)**, permitindo que você escolha a melhor estratégia de renderização para cada página ou componente:

- **SSR:** Com `getServerSideProps`, você pode renderizar uma página no servidor em cada requisição.
- **CSR:** Componentes ou páginas que dependem de interatividade podem ser renderizados no lado do cliente.
- **SSG:** Com `getStaticProps`, você pode gerar páginas estáticas no momento da build, que são servidas de forma extremamente rápida.

Essa flexibilidade é uma das maiores vantagens do Next.js, permitindo que você otimize sua aplicação para diferentes casos de uso e cenários.

## Configuração do Husky

Este projeto também utiliza o Husky para automatizar tarefas que garantem a qualidade do código antes de certos eventos do Git, como *commit* ou *push*. Os *hooks* configurados ajudam a garantir que o código está bem formatado e livre de erros de tipo antes de ser enviado ao repositório.

### Estrutura da Pasta `.husky`

- **`.gitignore`:** Ignora arquivos desnecessários dentro da pasta `.husky`.
- **`husky.sh`:** Script de inicialização usado para configurar o ambiente antes de executar os *hooks* do Git.
- **`pre-push`:** Executa checagens de linting e tipos TypeScript antes de permitir que um `git push` seja concluído.

Para mais detalhes, consulte a seção [Husky Setup](#husky-setup).

## Scripts Disponíveis

- `npm run dev`: Inicia o servidor de desenvolvimento Next.js.
- `npm run build`: Cria uma versão otimizada para produção do projeto.
- `npm run start`: Inicia o servidor em modo de produção após o build.
- `npm run lint`: Executa o ESLint para checar problemas de estilo e código.
- `npm run type-check`: Verifica se há erros de tipo no código TypeScript.

## Como Contribuir

Se você deseja contribuir para este projeto, siga os passos abaixo:

1. Fork o repositório.
2. Crie uma nova branch (`git checkout -b feature/nova-feature`).
3. Faça suas alterações e adicione commits (`git commit -m 'Adiciona nova feature'`).
4. Faça o push para a branch (`git push origin feature/nova-feature`).
5. Abra um Pull Request.

Certifique-se de que todas as alterações passaram nas verificações de linting e tipos antes de abrir um PR.


