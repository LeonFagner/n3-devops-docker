# N3 – Pipeline DevOps com Forgejo, CI/CD e Docker

Este projeto faz parte da avaliação N3, cujo objetivo é demonstrar um fluxo DevOps completo utilizando ferramentas **open-source** e **auto-hospedadas**, sem qualquer uso de SaaS.  
Toda a solução foi montada e executada **localmente** utilizando:

- **Forgejo** (Git + CI/CD)
- **Forgejo Runner / Drone CI (dependendo da instalação)**
- **Docker**
- **Registry local (Forgejo Container Registry ou Docker Registry local)**

---

## 🚀 Objetivo da Entrega

O pipeline configurado precisa executar automaticamente:

1. **Testes unitários**
2. **Build da imagem Docker**
3. **Push da imagem para o registry local (se configurado)**
4. **Deploy automático** — execução de um container com a imagem recém-gerada
5. **API rodando dentro do container**

Todos esses itens foram implementados.

---

## 🧰 Ferramentas Utilizadas

| Ferramenta | Função |
|-----------|--------|
| **Forgejo** | Repositório Git + orquestração de CI/CD |
| **Forgejo Runner / Drone** | Execução dos pipelines |
| **Docker** | Build, execução e gerenciamento de containers |
| **Registry local** | Armazenamento da imagem Docker gerada (opcional) |

> ⚠️ Forgejo está hospedado localmente dentro de um container.  
> Por isso, o repositório **não possui link público**, conforme exigência da atividade (somente soluções auto-hospedadas).

---

## 🔧 Fluxo do Pipeline

O pipeline foi configurado para executar o seguinte fluxo:

1. **Clonagem do repositório**
2. **Instalação das dependências**
3. **Execução dos testes unitários**
4. **Build da imagem Docker**
5. (Opcional) **Push para o registry local**
6. **Deploy automático** via:
   ```bash
   docker run -d -p XXXX:XXXX nome-da-imagem
