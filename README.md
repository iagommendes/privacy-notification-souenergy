# Privacy Notification - SouEnergy 🌞

## Descrição Geral

Este projeto é uma aplicação web desenvolvida para a SouEnergy, uma empresa de energia solar. A aplicação permite que os usuários façam login, visualizem um dashboard com informações relevantes sobre seus sistemas de energia solar, e aceitem uma política de privacidade através de um modal. O backend é simulado usando JSON Server para prototipagem rápida.

### Funcionalidades Principais

- **Login Simulado**: Permite que usuários façam login usando credenciais fictícias armazenadas no JSON Server.
- **Modal de Política de Privacidade**: Exibe um modal após o login, solicitando que o usuário aceite a política de privacidade.
- **Dashboard de Energia Solar**: Exibe informações sobre monitoramento de painéis, relatórios de economia e suporte técnico.
- **Painel Administrativo**: Permite visualizar quais usuários aceitaram a política de privacidade.

## 🚀 Instalação e Configuração

### Pré-requisitos

- Node.js e npm instalados em sua máquina. [Download Node.js](https://nodejs.org/)

### Passos para Instalação

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/iagommendes/privacy-notification-souenergy.git
   cd privacy-notification-souenergy
   ```

2. **Instale as dependências**:
   ```bash
   npm install
   ```

3. **Crie o arquivo `db.json`** na raiz do projeto com o seguinte conteúdo:
   ```json
   {
     "users": [
       {
         "id": "1",
         "name": "User1",
         "password": "password123",
         "acceptedPolicy": false
       },
       {
         "id": "2",
         "name": "User2",
         "password": "password456",
         "acceptedPolicy": false
       }
     ]
   }
   ```

4. **Inicie o JSON Server**:
   - Execute o JSON Server:
     ```bash
     json-server --watch db.json --port 3000
     ```

5. **Inicie o servidor de desenvolvimento do Vite**:
   ```bash
   npm run dev
   ```

6. **Acesse a aplicação**:
   - Abra o navegador e vá para `http://localhost:5173`. ou rota informada pelo Vite.

## 🧪 Exemplos de Testes

### Teste de Login

1. Acesse a aplicação no navegador.
2. Use as credenciais fictícias para fazer login:
   - **Usuário**: User1
   - **Senha**: password123
3. Verifique se o modal de política de privacidade é exibido após o login.

### Teste de Aceitação da Política

1. Após o login, clique no botão "Aceitar" no modal.
2. Verifique se o modal desaparece e a aceitação é registrada no JSON Server.

### Teste do Painel Administrativo

1. Navegue até o painel administrativo.
2. Verifique se os usuários que aceitaram a política são listados corretamente.

## 🏗️ Estrutura de Código e Arquitetura

### Estrutura de Pastas

```
privacy-notification-souenergy/
├── public/
├── src/
│   ├── assets/
│   ├── components/
│   ├── views/
│   ├── App.vue
│   ├── main.js
│   └── router.js
├── db.json
├── .gitignore
├── index.html
├── package.json
├── vite.config.js
└── README.md
```

### Descrição

- **public/**: Contém arquivos estáticos.
- **src/**: Diretório principal do código-fonte.
  - **assets/**: Armazena imagens e estilos globais.
  - **components/**: Contém componentes Vue reutilizáveis.
  - **views/**: Contém as views principais da aplicação (Login, Dashboard, Admin).
  - **App.vue**: Componente raiz da aplicação.
  - **main.js**: Ponto de entrada da aplicação.
  - **router.js**: Configuração de rotas usando Vue Router.

### Arquitetura

- **Vue.js**: Framework JavaScript progressivo para construir interfaces de usuário.
- **Vite**: Ferramenta de construção rápida para desenvolvimento de aplicações Vue.js.
- **JSON Server**: Simula um backend RESTful para prototipagem rápida.

## 📌 Observações

- Este projeto é uma demonstração básica e não deve ser usado em produção sem melhorias de segurança, como autenticação segura e gerenciamento de sessões.
- O JSON Server é usado apenas para fins de prototipagem e não substitui um backend real.
