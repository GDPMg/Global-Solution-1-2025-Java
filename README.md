# ⚡ EnergiaLert – Monitoramento de Quedas de Energia em São Paulo

Projeto desenvolvido para a disciplina de **Programação Orientada a Serviços**, com foco em **quebras de energia pública** e simulação de monitoramento via consumo de API REST.

---

## 👥 Grupo

- **Guilherme Dal Posolo Matheus** – RM 98694  
- **Guilherme Faustino Vargas** – RM 98278  
- **Ryan Perez Pacheco** – RM 98782  

---

## ✅ Observações

🔎 Um fato muito interessante sobre o projeto é que os dados utilizados na API do Mocky são **dados reais**, coletados por nosso sistema de **monitoramento** desenvolvido na entregade IOT.

📡 Nesse sistema, monitoramos postes de iluminação pública nas ruas para detectar **quedas de energia**, com o objetivo de:

- Acionar autoridades responsáveis;
- Alertar usuários afetados;
- Apoiar futuras decisões de infraestrutura urbana.

💡 Este projeto é uma continuação prática dessa solução, integrando **serviços REST** e **visualização em tempo real**, reforçando a importância da Arquitetura Orientada a Serviços no contexto urbano.

---

## 📌 Funcionalidades Implementadas

- ✅ Consumo de API externa (Mocky) com dados em JSON
- ✅ Organização modular por camadas: controller, service e model
- ✅ Endpoints RESTful para:
  - Listagem completa de eventos
  - Filtros por tipo (`queda` / `retorno`)
  - Filtros por poste
  - Contagem de eventos por tipo ou poste
  - Último evento registrado
- ✅ Tratamento de erros com mensagem amigável
- ✅ Página web com dashboard (tabela + gráfico com Chart.js)
- ✅ Integração com API de geocodificação (Nominatim) para exibir endereço formatado a partir das coordenadas

---

## 🏗️ Como rodar o projeto

1. **Pré-requisitos:**
   - Java 17+
   - Maven
   - Spring Boot

### Acessar no navegador

- API: [http://localhost:8080/energia](http://localhost:8080/energia)  
- Dashboard: [http://localhost:8080/dashboard](http://localhost:8080/dashboard)

---

## 🔗 Endpoints REST para testes

| Método | Rota | Descrição |
|--------|------|-----------|
| GET | `/energia/eventos` | Lista todos os eventos |
| GET | `/energia/eventos/tipo/queda` | Lista eventos do tipo "queda" |
| GET | `/energia/eventos/poste/Poste 1` | Lista eventos do Poste 1 |
| GET | `/energia/eventos/contagem/tipo` | Retorna a contagem por tipo |
| GET | `/energia/eventos/contagem/poste` | Retorna a contagem por poste |
| GET | `/energia/eventos/ultimo` | Retorna o evento mais recente |
| GET | `/energia/eventos/com-endereco` | Lista eventos com endereço formatado (via geocodificação reversa) |

---

## 📊 Dashboard Web

Acesse o dashboard visual:  
[http://localhost:8080/dashboard](http://localhost:8080/dashboard)

Inclui:
- ✔️ Tabela com todos os eventos  
- ✔️ Gráfico de barras com distribuição de quedas e retornos

```
src/
└── main/
    ├── java/
    │   └── br/com/energialert/
    │       ├── controller/         # Endpoints REST
    │       ├── service/            # Regras de negócio
    │       ├── model/              # Representação dos dados
    │       ├── client/             # Consumo da API de geocodificação
    │       ├── exception/          # Exceções personalizadas
    │       └── handler/            # Tratamento global de erros
    └── resources/
        ├── templates/              # Arquivos HTML (Thymeleaf)
        ├── static/                 # JS, CSS, imagens se necessário
        └── application.properties  # Configurações da aplicação
```

