# Política de Segurança - Gestão Nuvia Odontologia

### Alerta Técnico Atual (Auditado por Sentinel)
Durante uma análise passiva de segurança, identificamos uma configuração de risco alto que requer remediação imediata:

* **Vulnerabilidade:** Exposição de Arquivos Source Map (`.js.map`) em ambiente público.
* **Localização:** Diretório `dev-dist/assets/`.
* **Risco:** Permite engenharia reversa total do código-fonte original, expondo endpoints de API, lógica de negócio e potenciais credenciais hardcoded.
* **Impacto LGPD:** Facilita a descoberta de vetores de exfiltração de dados sensíveis de saúde.
* **Credenciais expostas** Duas credenciais admin@nuvia.com e compras@nuvia.com foram expostas

## Práticas de Hardening Recomendadas
1.  **Remover Artefatos de Build:** O diretório `dev-dist` não deve ser público.
2.  **Configuração de Build:** Ajustar o bundler (Vite/Webpack) para `sourcemap: false` em builds de produção.
3.  **Git Hygiene:** Adicionar arquivos `.map` e pastas de distribuição ao `.gitignore`.

---
