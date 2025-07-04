# AjudaSolidária - Plataforma de Doações

Uma plataforma completa para conectar doadores, beneficiários e organizações, facilitando doações e ações solidárias.

## 🚀 Funcionalidades

- **Sistema de autenticação JWT** com diferentes tipos de usuário
- **Cadastro e gerenciamento de itens** para doação
- **Sistema de solicitações** para beneficiários
- **Criação de campanhas** por organizações
- **Dashboard personalizado** por tipo de usuário
- **Interface responsiva** e acessível
- **Sistema CRUD completo** para todas as entidades

## 👥 Tipos de Usuário

### Doador
- Cadastrar itens para doação
- Visualizar solicitações
- Participar de campanhas

### Beneficiário
- Solicitar itens disponíveis
- Visualizar status das solicitações
- Participar de campanhas

### Organização
- Criar e gerenciar campanhas
- Aprovar/rejeitar solicitações
- Gerar relatórios

## 📋 Pré-requisitos

- Node.js 16+
- npm ou yarn

## 🛠️ Instalação

### 1. Clone o repositório
```bash
git clone https://github.com/seu-usuario/ajuda-solidaria.git
cd ajuda-solidaria
```

### 2. Instale as dependências
```bash
npm install
```

### 3. Inicialize o banco de dados
```bash
npm run init-db
```

### 4. Inicie o servidor
```bash
npm start
```

Para desenvolvimento com auto-reload:
```bash
npm run dev
```

O servidor estará rodando em `http://localhost:3000`

## 🗄️ Estrutura do Banco de Dados

### Tabelas

- **usuarios**: Dados dos usuários (doadores, beneficiários, organizações)
- **itens**: Itens disponíveis para doação
- **solicitacoes**: Solicitações de itens por beneficiários
- **campanhas**: Campanhas criadas por organizações

### Dados de Exemplo

O sistema vem com dados de exemplo pré-cadastrados:

**Credenciais de teste:**
- **Doador**: `joao@email.com` / `123456`
- **Beneficiário**: `maria@email.com` / `123456`
- **Organização**: `contato@esperanca.org` / `123456`

## 📁 Estrutura do Projeto

```
ajuda-solidaria/
├── public/
│   ├── index.html          # Página principal
│   ├── css/
│   │   └── style.css       # Estilos da aplicação
│   └── js/
│       ├── api.js          # Classe para gerenciar API
│       └── app.js          # Lógica principal da aplicação
├── database/
│   ├── init.js             # Script de inicialização do banco
│   └── ajuda_solidaria.db  # Banco SQLite (criado automaticamente)
├── server.js               # Servidor Express
├── package.json            # Dependências e scripts
└── README.md               # Este arquivo
```

## 🔌 API Endpoints

### Autenticação
- `POST /api/register` - Registrar usuário
- `POST /api/login` - Login de usuário

### Usuários
- `GET /api/user/profile` - Obter perfil do usuário
- `PUT /api/user/profile` - Atualizar perfil

### Itens
- `GET /api/items` - Listar itens disponíveis
- `POST /api/items` - Criar item (apenas doadores)
- `PUT /api/items/:id` - Atualizar item
- `DELETE /api/items/:id` - Excluir item

### Solicitações
- `GET /api/requests` - Listar solicitações
- `POST /api/requests` - Criar solicitação (apenas beneficiários)
- `POST /api/requests/:id/approve` - Aprovar solicitação (apenas organizações)
- `POST /api/requests/:id/reject` - Rejeitar solicitação (apenas organizações)

### Campanhas
- `GET /api/campaigns` - Listar campanhas ativas
- `POST /api/campaigns` - Criar campanha (apenas organizações)
- `POST /api/campaigns/:id/donate` - Fazer doação para campanha

### Estatísticas
- `GET /api/stats` - Estatísticas gerais do sistema

## 🎨 Design e UX

### Características
- **Design responsivo** para desktop, tablet e mobile
- **Paleta de cores suave** (verde, azul, branco)
- **Tipografia clara** (Poppins)
- **Ícones intuitivos** (Font Awesome)
- **Animações suaves** e feedback visual

### Componentes
- **Header fixo** com navegação
- **Hero section** com call-to-action
- **Seções informativas** sobre o projeto
- **Modais** para login, cadastro e dashboard
- **Dashboard personalizado** por tipo de usuário

## 🔒 Segurança

- **Autenticação JWT** com tokens seguros
- **Hash de senhas** com bcrypt
- **Validação de dados** em todas as entradas
- **Proteção de rotas** por tipo de usuário
- **Sanitização de inputs** para prevenir XSS

## 🚀 Deploy

### Para Produção

1. **Configure as variáveis de ambiente:**
```bash
NODE_ENV=production
PORT=3000
JWT_SECRET=sua_chave_super_secreta
```

2. **Use um process manager como PM2:**
```bash
npm install -g pm2
pm2 start server.js --name "ajuda-solidaria"
```

3. **Configure um proxy reverso (nginx/apache)** se necessário

### Para Desenvolvimento

```bash
npm run dev
```

## 🧪 Testando o Sistema

### Fluxo de Teste Recomendado

1. **Acesse a página inicial** e explore as seções
2. **Faça cadastro** como doador
3. **Cadastre alguns itens** para doação
4. **Faça logout** e cadastre-se como beneficiário
5. **Solicite itens** disponíveis
6. **Entre como organização** para aprovar solicitações
7. **Crie uma campanha** e teste as funcionalidades

### Funcionalidades por Tipo de Usuário

**Doador:**
- Cadastrar itens
- Visualizar solicitações
- Participar de campanhas

**Beneficiário:**
- Solicitar itens
- Acompanhar status das solicitações
- Participar de campanhas

**Organização:**
- Criar campanhas
- Aprovar/rejeitar solicitações
- Gerar relatórios

## 📈 Funcionalidades Futuras

- [ ] Sistema de notificações em tempo real
- [ ] Upload de imagens para itens
- [ ] Sistema de avaliação e feedback
- [ ] Integração com redes sociais
- [ ] App mobile (React Native)
- [ ] Sistema de geolocalização
- [ ] Relatórios avançados com gráficos
- [ ] Sistema de mensagens entre usuários

## 🤝 Contribuindo

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

---

**Nota:** Este é um projeto educacional desenvolvido para demonstrar conceitos de desenvolvimento web, incluindo frontend, backend, banco de dados e boas práticas de programação. 