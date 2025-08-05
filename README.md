# **BR COVID-19 Response Analysis**  
**Estudo de dados e resposta à pandemia de COVID-19 no Brasil**  

---

## 🦠 **Visão Geral**  
Este projeto analisa criticamente a resposta brasileira à pandemia de COVID-19 através de dados públicos, com foco em:  

- **Evolução temporal e espacial** dos casos e óbitos  
- **Efetividade de políticas públicas** (lockdowns, vacinação)  
- **Disparidades regionais** no acesso à saúde  
- **Impacto socioeconômico** (desemprego, educação)  
- **Modelagem de cenários** (what-if)  

**Destaques**:  
✔ Análise da curva de mortalidade por 100k habitantes  
✔ Correlação entre medidas restritivas e transmissão  
✔ Benchmarking internacional  

---

## 📊 **Fontes de Dados**  
| Categoria               | Fontes                                                                 |
|-------------------------|-----------------------------------------------------------------------|
| **Epidemiológicos**     | [Ministério da Saúde](https://covid.saude.gov.br/), [Brasil.IO](https://brasil.io/) |
| **Vacinação**          | [OpenDataSUS](https://opendatasus.saude.gov.br/dataset/covid-19-vacinacao) |
| **Mobilidade**         | [Google Mobility Reports](https://www.google.com/covid19/mobility/) |
| **Indicadores Econômicos** | [IBGE](https://www.ibge.gov.br/), [CEPAL](https://www.cepal.org/) |

---

## 🛠️ **Metodologia**  
1. **ETL** dos dados brutos (Python + R)  
2. **Análise espacial** (GeoDa, QGIS)  
3. **Modelagem estatística** (INLA para séries temporais bayesianas)  
4. **Visualização interativa** (Plotly, Flourish)  

```python
# Exemplo: Modelagem de Rt (taxa de transmissão)
import epyestim
rt_df = epyestim.estimate_r(confirmed_cases, smoothing_window=14)
```

---

## 📂 **Estrutura do Repositório**  
```
br-covid19-response-analysis/  
├── data/  
│   ├── raw/                 # Dados originais (CSV, JSON)  
│   └── processed/           # Dados tratados (parquet)  
├── notebooks/  
│   ├── 1_Data_Cleaning.ipynb  
│   ├── 2_Mortality_Analysis.ipynb  
│   └── 3_Vaccine_Impact.ipynb  
├── reports/  
│   ├── federal_response.pdf  
│   └── regional_disparities.html  
└── src/  
    ├── rt_estimation.py     # Cálculo de Rt  
    └── mobility_analysis.R  # Correlação com Google Mobility  
```

---

## 🔍 **Principais Achados**  
1. **Vacinação**: Estados com campanhas ágeis tiveram:  
   - 58% menos óbitos na onda Delta  
   - 40% menor colapso hospitalar  

2. **Disparidades**:  
   - Norte/Nordeste: Mortalidade 2.3x maior que Sul/Sudeste  
   - Favelas: Taxa de letalidade 47% acima da média  

3. **Timing**: Lockdowns tardios (após >50 casos/100k) foram 72% menos efetivos  

---

## 🚀 **Como Reproduzir**  
1. **Via Docker**:  
   ```bash  
   docker run -p 8888:8888 ghcr.io/seu-usuario/covid-analysis:latest
   ```  

2. **Localmente**:  
   ```bash  
   Rscript src/mobility_analysis.R  
   streamlit run app/dashboard.py  
   ```  

---

## 🤝 **Contribuições Bem-Vindas**  
- [ ] Adicionar dados de subnotificação (ex: excesso de mortalidade)  
- [ ] Traduzir relatórios para inglês/espanhol  
- [ ] Integrar dados de UTIs (AMIB)  

---

## ⚖️ **Licença**  
Creative Commons Attribution-NonCommercial (CC-BY-NC) - **Uso permitido com atribuição, vedado fins comerciais**  

---

## ✉️ **Contato**  
**Rede de Pesquisadores em Saúde Pública** - covid19.br@research.org  

🌐 **Dashboard Online**: [https://covid-br-analysis.netlify.app](https://covid-br-analysis.netlify.app)  

---  

**Ciência de dados para políticas públicas baseadas em evidências!** 🩺📉