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

## Licença

Este projeto está licenciado sob a Licença MIT. Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.
