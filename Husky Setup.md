# Husky Setup

Este projeto utiliza o [Husky](https://typicode.github.io/husky/#/) para gerenciar e automatizar tarefas usando *Git hooks*. Abaixo estão os detalhes de configuração dos arquivos encontrados na pasta `.husky`.

## O que é Husky?

Husky é uma ferramenta que facilita a configuração de *Git hooks* em projetos, permitindo que você automatize tarefas como linting, testes, e checagens de tipos antes de realizar certos comandos do Git, como `commit` ou `push`. Isso ajuda a garantir a qualidade do código e a consistência no repositório.

## Estrutura da Pasta `.husky`

### `.gitignore`

- Contém a regra `*`, que indica que todos os arquivos na pasta `.husky` são ignorados pelo Git.
- Isso é usado para garantir que apenas os arquivos necessários sejam incluídos no controle de versão, mantendo o repositório limpo.

### `husky.sh`

- Este é o script de inicialização que Husky usa para configurar o ambiente antes de executar um *Git hook*.
- O script realiza as seguintes tarefas:
  1. Verifica se a variável `husky_skip_init` está definida. Se estiver, o script não faz nada e termina.
  2. Caso contrário, carrega o arquivo de configuração `.huskyrc`, se este existir.
  3. Executa o próprio script do *hook* (como `pre-push`) e captura o código de saída.
  4. Exibe mensagens de erro caso o comando do *hook* falhe ou não seja encontrado.

### `pre-push`

- Este é um exemplo de *hook* configurado para ser executado antes de um `git push`.
- O script realiza as seguintes etapas:
  1. Executa o script `husky.sh` para preparar o ambiente.
  2. Executa a checagem de linting com `npx eslint src` para garantir que o código segue as regras de estilo definidas.
  3. Executa a checagem de tipos TypeScript com `npx tsc --noEmit --skipLibCheck` para verificar se há erros de tipo no código sem gerar arquivos de saída.
  4. Exibe mensagens no console para indicar o progresso e os resultados das checagens.

## Por que usar Husky?

- **Qualidade do Código:** Garante que o código segue padrões de estilo e não contém erros de tipo antes de ser enviado ao repositório.
- **Automatização:** Reduz a necessidade de verificações manuais, automatizando tarefas repetitivas e minimizando erros humanos.
- **Integração com CI/CD:** Pode ser integrado em processos de CI/CD para garantir que apenas código de qualidade seja submetido.

## Como Usar

Se você deseja ajustar ou adicionar novos *hooks*, basta criar scripts adicionais na pasta `.husky` com o nome do *hook* Git correspondente. Husky cuidará do resto!

Para mais informações sobre como configurar e utilizar Husky, consulte a [documentação oficial](https://typicode.github.io/husky/#/).

---

*Nota:* Certifique-se de que o Husky está instalado e configurado corretamente em seu projeto para que os *hooks* funcionem como esperado.
