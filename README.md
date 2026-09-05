# Match Simulation API Data

![License](https://img.shields.io/badge/license-MIT-green)
![Format](https://img.shields.io/badge/format-JSON-blue)
![Status](https://img.shields.io/badge/status-Dados%20Estáticos-orange)

Este repositório fornece um dataset JSON (`matches.json`) contendo dados simulados de partidas, útil para:
- **Testes de APIs** esportivas ou de jogos
- **Simulações** de campeonatos e torneios
- **Análise de dados** e visualizações
- **Desenvolvimento frontend** com dados realistas
- **Prototipagem** de aplicativos esportivos

## 📄 Arquivo: matches.json

Contém dados estruturados representando detalhes de partidas, times, placares e eventos.

### Estrutura dos Dados

```json
[
  {
    "id": 1,
    "homeTeam": "Time A",
    "awayTeam": "Time B",
    "homeScore": 2,
    "awayScore": 1,
    "date": "2024-01-15",
    "competition": "Campeonato Brasileiro",
    "stadium": "Estádio do Morumbi",
    "attendance": 45000,
    "events": [
      {"minute": 23, "type": "goal", "team": "home", "player": "João Silva"},
      {"minute": 45, "type": "yellow_card", "team": "away", "player": "Carlos Santos"},
      {"minute": 67, "type": "goal", "team": "home", "player": "Pedro Oliveira"},
      {"minute": 89, "type": "goal", "team": "away", "player": "Lucas Ferreira"}
    ]
  }
]
```

### Campos Principais

| Campo | Tipo | Descrição |
|-------|------|-----------|
| `id` | Integer | Identificador único da partida |
| `homeTeam` | String | Nome do time da casa |
| `awayTeam` | String | Nome do time visitante |
| `homeScore` | Integer | Gols do time da casa |
| `awayScore` | Integer | Gols do time visitante |
| `date` | String (ISO 8601) | Data da partida |
| `competition` | String | Nome da competição/campeonato |
| `stadium` | String | Estádio onde ocorreu |
| `attendance` | Integer | Público presente |
| `events` | Array | Lista de eventos da partida (gols, cartões, substituições) |

## 🚀 Como Usar

### Consumo direto do JSON
```bash
# Clone o repositório
git clone https://github.com/paulorabelo/matches-sim-api.git

# Use o arquivo matches.json diretamente no seu código
```

### Exemplo em JavaScript
```javascript
fetch('matches.json')
  .then(response => response.json())
  .then(matches => {
    // Filtrar partidas do time da casa
    const homeWins = matches.filter(m => m.homeScore > m.awayScore);
    console.log('Vitórias em casa:', homeWins.length);
  });
```

### Exemplo em Python
```python
import json

with open('matches.json', 'r', encoding='utf-8') as f:
    matches = json.load(f)

# Partidas com mais de 3 gols
high_scoring = [m for m in matches if (m['homeScore'] + m['awayScore']) > 3]
print(f'Partidas com >3 gols: {len(high_scoring)}')
```

## 📊 Casos de Uso

| Caso de Uso | Descrição |
|-------------|-----------|
| **Teste de API** | Mock de endpoint `/matches` para desenvolvimento frontend |
| **Dashboard Esportivo** | Dados para gráficos de desempenho, tabelas de classificação |
| **Machine Learning** | Treino de modelos de previsão de resultados |
| **App Mobile** | Dados offline para app de acompanhamento de times |
| **Ensino** | Dataset realista para aulas de análise de dados |

## 🔧 Personalização

Para gerar seus próprios dados, você pode:
1. Modificar `matches.json` diretamente
2. Criar scripts de geração baseados nas regras do seu esporte
3. Integrar com APIs reais (ex: Football-Data.org, API-Football)

## 📝 Licença

Este dataset é fornecido sob licença **MIT**. Livre para uso, modificação e distribuição.

## 👨‍💻 Autor

**Paulo Rabelo**
- GitHub: [@paulorabelo](https://github.com/paulorabelo)
- Blog: [blog.paulorabelo.dev.com.br](https://blog.paulorabelo.dev.com.br)
- LinkedIn: [Paulo Rabelo](https://www.linkedin.com/in/paulorabelooficial/)

---

*Dataset criado para fins de desenvolvimento, teste e aprendizado.*
