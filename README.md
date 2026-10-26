# Ciclo de Vida de um Projeto no GitHub: Meu Guia Prático

Aprender a usar o GitHub e o Git é fundamental para quem deseja crescer na área de tecnologia. Assim como comentei em meus estudos sobre a evolução da carreira e adaptabilidade no mercado, ter o domínio das ferramentas certas faz toda a diferença para demonstrar nosso trabalho. Este guia resume, de forma simples e direta, o passo a passo de como configurar o ambiente e gerenciar um projeto do zero até as suas atualizações diárias.

---

## Sessão 1: O Passo a Passo da Criação e Envio

### Preparação Prévia: Identidade e Chave SSH

Antes de começar o primeiro projeto, é necessário configurar o terminal do computador (PowerShell ou Git Bash) para que o Git saiba quem está fazendo as alterações e consiga se comunicar com o GitHub de forma segura.

1. **Definição da Identidade Global:**  
   No terminal, informo meu nome e o mesmo e-mail cadastrado na minha conta do GitHub:
   ```bash
   git config --global user.name "Seu Nome"
   git config --global user.email "seu_email@exemplo.com"
   ```

2. **Criação da Chave SSH (Autenticação Segura):**  
   Para enviar arquivos sem precisar digitar a senha toda vez, gero uma chave SSH de acesso com o comando:
   ```bash
   ssh-keygen -t ed25519 -C "seu_email@exemplo.com"
   ```
   Aperto *Enter* nas confirmações para aceitar os padrões. Em seguida, exibo a chave gerada com:
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```
   Copio todo o conteúdo exibido e cole no site do GitHub acessando: **Settings > SSH and GPG keys > New SSH key**.

---

### O Início: Criando o Repositório na Nuvem

Com o ambiente pronto, crio o repositório diretamente na plataforma do GitHub:

1. Clico no botão **"+"** no canto superior direito e seleciono **"New repository"**.
2. Defino um **nome claro e simples** para o projeto (sem espaços ou acentos).
3. Posso adicionar uma breve descrição opcional sobre o objetivo do projeto.
4. Escolho a visibilidade como **Pública** (para que outras pessoas ou recrutadores possam visualizar meu trabalho) ou **Privada**.
5. Clico em **"Create repository"** para gerar o link remoto do repositório (SSH ou HTTPS).

---

### A Conexão: Inicializando e Vinculando a Pasta Local

Agora, transformo a pasta do meu computador em um repositório Git local e conecto-a à nuvem:

1. Navego até a pasta do projeto pelo terminal:
   ```bash
   cd caminho/para/sua/pasta
   ```

2. Inicializo a pasta como um repositório Git e defino o ramo principal como `main`:
   ```bash
   git init
   git branch -M main
   ```

3. Vinculo a minha pasta local ao endereço remoto gerado pelo GitHub:
   ```bash
   git remote add origin URL_DO_SEU_REPOSITORIO
   ```

---

### O Primeiro Envio: Subindo os Arquivos

Para registrar o projeto e enviá-lo à página do GitHub, sigo estes comandos:

1. **Criar o arquivo inicial de documentação (opcional via terminal):**
   ```bash
   echo "# Meu Primeiro Projeto" > README.md
   ```

2. **Adicionar os arquivos para a área de preparação (staging):**
   ```bash
   git add .
   ```

3. **Registrar o momento da alteração com uma mensagem explicativa:**
   ```bash
   git commit -m "Primeiro commit"
   ```

4. **Enviar os dados para a nuvem:**
   ```bash
   git push -u origin main
   ```

---

## Sessão 2: A Anatomia do README Perfeito

### Propósito

O arquivo `README.md` funciona como a capa e o cartão de visitas do projeto. O objetivo dele é explicar de forma rápida o que o projeto faz, qual problema ele resolve e como executá-lo. Seu público-alvo inclui outros desenvolvedores, professores e recrutadores que acessam o repositório em busca de contexto.

### 5 Dados Fundamentais que Não Podem Faltar

1. **Título e Descrição do Projeto:** Nome principal acompanhado de um resumo simples sobre a ideia.
2. **Tecnologias Utilizadas:** Lista com as linguagens, bibliotecas ou ferramentas usadas (ex: HTML, CSS, JavaScript).
3. **Como Instalar e Rodar o Projeto:** O passo a passo dos comandos necessários para testar o projeto localmente.
4. **Status do Desenvolvimento:** Indicação se o projeto está "Concluído", "Em Andamento" ou em fase de testes.
5. **Licença ou Autoria:** Informações sobre quem desenvolveu e os direitos de uso do código.

### O Poder do Markdown

Utilizamos a linguagem Markdown (`.md`) porque ela é muito leve e fácil de escrever. Com marcações simples (como `#` para títulos, `**` para negrito e `-` para listas), conseguimos deixar a documentação limpa, organizada e com um visual agradável direto na página do GitHub.

---

## Sessão 3: O Mapa das Atualizações (Commits e Pushes)

### GitHub Online (Navegador)
* **Como funciona:** Edito um arquivo diretamente no site do GitHub usando o ícone de lápis e salvo alterando a mensagem de commit no final da página.
* **Quando usar:** Para correções pequenas e rápidas no README ou detalhes no texto.
* **Limitações:** Não permite rodar ou testar o código e é ruim para atualizar vários arquivos juntos.

### Git via Linha de Comando (Terminal)
* **Como funciona:** Utilizo os comandos clássicos `git status`, `git add .`, `git commit -m "mensagem"` e `git push`.
* **Por que é tradicional:** Funciona em qualquer sistema operacional, dá controle total de cada etapa do envio e é o padrão da indústria.

### IDEs (Ex: VS Code)
* **Como funciona:** O próprio editor possui a aba de Controle de Versão (*Source Control*), onde seleciono os arquivos modificados, digito a mensagem e clico em "Commit" e "Sync Changes".
* **Experiência:** Muito prática para o dia a dia, pois junta a escrita do código e o controle de versão no mesmo lugar.

### GitHub Desktop
* **Como funciona:** Um programa visual onde é possível ver exatamente o que foi alterado em cada linha (em verde o que entrou, em vermelho o que foi removido).
* **Facilidade:** Excelente para quem quer acompanhar visualmente o que mudou antes de fazer o commit e push.

### A Filosofia da Atualização Contínua

Salvar o trabalho de forma contínua e em pequenas partes (com vários commits pequenos) é fundamental. Quando dividimos as atualizações em etapas curtas, fica muito mais simples entender a evolução do código, localizar a causa de algum erro e manter o projeto bem organizado no dia a dia.
