# Privacy Notification App 🔐📋

## Descrição do Projeto

O Privacy Notification App é uma aplicação web desenvolvida para gerenciar e notificar usuários sobre atualizações na política de privacidade de uma plataforma. O sistema permite:

- Autenticação de usuários
- Exibição de modal de notificação de privacidade
- Controle de aceitação de termos
- Painel administrativo para visualização de status de privacidade

## 🌟 Funcionalidades Principais

- Login de usuários
- Modal de notificação de política de privacidade
- Controle de aceitação de termos
- Grid de usuários com status de privacidade
- Autenticação e autorização

## 🛠 Tecnologias Utilizadas

- Vue.js
- Vuex (Gerenciamento de Estado)
- Vue Router
- Axios
- JSON Server (Mock Backend)
- Vuelidate (Validações)

## 📋 Pré-requisitos

- Node.js (v14 ou superior)
- npm (v6 ou superior)

## 🚀 Instalação

### Clonar o Repositório
```bash
git clone https://github.com/seu-usuario/privacy-notification-app.git
cd privacy-notification-app
```

### Instalar Dependências
```bash
npm install
```

## 🔧 Configuração

### Iniciar Mock Backend
```bash
# Em um terminal
npm run start-backend
```

### Iniciar Aplicação Vue
```bash
# Em outro terminal
npm run serve
```

## 🔐 Usuários de Teste

| Email | Senha | Papel |
|-------|-------|-------|
| joao@example.com | senha123 | Admin |
| maria@example.com | senha456 | Usuário |
| carlos@example.com | senha789 | Usuário |

## 📦 Estrutura do Projeto

```
privacy-notification-app/
│
├── mock-backend/       # Dados mockados
├── src/
│   ├── assets/         # Recursos estáticos
│   ├── components/     # Componentes Vue
│   ├── views/          # Páginas/Telas
│   ├── store/          # Gerenciamento de estado
│   ├── services/       # Serviços de API
│   └── router/         # Configurações de rota
└── scripts/            # Scripts auxiliares
```

## 🧪 Testes

### Executar Testes
```bash
npm run test
```

## 🚢 Deploy

O projeto está configurado com GitHub Actions para:
- Instalação de dependências
- Execução de testes
- Build da aplicação

## 🤝 Contribuição

1. Faça um fork do projeto
2. Crie sua feature branch (`git checkout -b feature/nova-funcionalidade`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/nova-funcionalidade`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 🐛 Problemas Conhecidos

- Autenticação é apenas mock
- Sem persistência real de dados
- Necessidade de implementar testes mais robustos

## 🔮 Próximos Passos

- [ ] Implementar autenticação real
- [ ] Adicionar mais testes unitários
- [ ] Criar design responsivo
- [ ] Integração com backend real

## 📞 Contato

Iago Mendes - iagommendes@gmail.com

Link do Projeto: [https://github.com/seu-usuario/privacy-notification-app](https://github.com/seu-usuario/privacy-notification-app)

---

<div align="center">
  Feito com ❤️ por [Iago Maciel]
</div>

## 🌈 Extras

### Captura de Tela

![Login Screen](screenshot-login.png)
![Privacy Modal](screenshot-privacy-modal.png)

### Badges

![Build Status](https://img.shields.io/github/workflow/status/seu-usuario/privacy-notification-app/CI)
![License](https://img.shields.io/github/license/seu-usuario/privacy-notification-app)
![Version](https://img.shields.io/github/package-json/v/seu-usuario/privacy-notification-app)