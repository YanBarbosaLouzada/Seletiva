# 📜 Sistema Automatizado de Emissão de Certificados em Lote

## 🎯 Sobre o Projeto

Sistema completo de automação para emissão de certificados em lote, desenvolvido com N8N e interface web no Lovable. A solução permite processar planilhas com dados de alunos, gerar certificados personalizados em PDF e enviá-los automaticamente por e-mail e WhatsApp.

## 🚀 Demonstração

**🔗 Acesse a aplicação:** [https://certificate-batch-forge.lovable.app/](https://certificate-batch-forge.lovable.app/)

**🎥 Vídeo demonstrativo:** 

https://github.com/user-attachments/assets/25aeca9c-e643-436e-911e-8ea117c6cc6a





## ⚙️ Funcionalidades

### 📊 Etapa 1: Interface de Upload e Processamento
- **Upload de Planilha**: Interface intuitiva para upload de arquivos Excel/CSV
- **Identificação Automática**: Sistema identifica automaticamente as colunas necessárias
- **Filtragem Inteligente**: Processa apenas alunos com status "SIM" na coluna de certificados
- **Formatação de Dados**:
  - Nome: Conversão automática para letras maiúsculas
  - Remoção de strings indesejadas (ex: "copy")
  - CPF: Formatação com pontuação (XXX.XXX.XXX-XX)
  - Complemento automático com "0" inicial para CPFs com menos de 11 dígitos

### 🎨 Etapa 2: Geração de Certificados
- **Upload de Template**: Possibilidade de usar modelos personalizados de certificado
- **Geração em Lote**: Produção automática de múltiplos certificados
- **Centralização de Nome**: Nome do aluno perfeitamente centralizado no certificado
- **Formato PDF**: Certificados gerados em formato PDF de alta qualidade
- **Integração N8N/Make**: Fluxo de automação robusto e escalável

### 📧 Etapa 3: Distribuição Automática
- **Envio por E-mail**: 
  - Integração com API do Gmail
  - Identificação automática da coluna de e-mail
  - Disparo em massa sem erros
  - Certificado anexado em PDF
- **Notificação WhatsApp**:
  - Envio automático de notificação
  - Informa o aluno sobre disponibilidade do certificado
  - Baseado no número de telefone da planilha

## 📋 Estrutura de Dados Necessária

A planilha de entrada deve conter as seguintes colunas:

| Coluna | Descrição | Obrigatório |
|--------|-----------|-------------|
| Nome | Nome completo do aluno | ✅ |
| CPF | CPF do aluno (com ou sem formatação) | ✅ |
| Telefone | Número de WhatsApp | ✅ |
| E-mail | E-mail para envio do certificado | ✅ |
| Certificado | Status "SIM" ou "NÃO" | ✅ |

## 🔄 Fluxo de Trabalho

```
1. Upload da Planilha
   ↓
2. Processamento e Validação dos Dados
   ↓
3. Formatação Automática (Nome, CPF)
   ↓
4. Geração dos Certificados em PDF
   ↓
5. Envio por E-mail (Gmail API)
   ↓
6. Notificação via WhatsApp
```

## 🛠️ Tecnologias Utilizadas

- **N8N**: Automação de workflows
- **Lovable**: Interface web responsiva
- **Gmail API**: Envio de e-mails em massa
- **WhatsApp API**: Notificações automáticas
- **PDF Generation**: Geração de certificados

## 📦 Como Usar

1. Acesse a aplicação: [certificate-batch-forge.lovable.app](https://certificate-batch-forge.lovable.app/)
2. Faça upload da sua planilha com os dados dos alunos
3. Faça upload do template do certificado (opcional)
4. Clique em "Processar" e aguarde a geração
5. Os certificados serão enviados automaticamente por e-mail
6. Os alunos receberão notificação via WhatsApp

## ✨ Diferenciais

- ✅ Processamento totalmente automatizado
- ✅ Interface intuitiva e fácil de usar
- ✅ Validação e formatação automática de dados
- ✅ Envio em massa sem erros
- ✅ Múltiplos canais de comunicação (E-mail + WhatsApp)
- ✅ Escalável para grandes volumes

## 📝 Observações

- Certifique-se de que a coluna "Certificado" contenha "SIM" para os alunos que devem receber o certificado
- CPFs podem ser inseridos com ou sem formatação
- Nomes serão automaticamente formatados para maiúsculas
- O sistema remove automaticamente textos indesejados como "copy"

## 🚧 Desafios e Limitações do Projeto

Durante o desenvolvimento deste sistema, alguns desafios foram enfrentados:

### ⚠️ Limitações das Plataformas
- **Restrições de API**: Gmail API e WhatsApp API(twilo) também possuem quotas diárias de envio
- **Impacto**: Para volumes muito grandes de certificados, pode ser necessário processar em lotes ou aguardar reset dos limites diários

### 📚 Curva de Aprendizado
- **Conhecimento básico em N8N**: O projeto foi desenvolvido com conhecimento inicial na plataforma
- **Complexidade dos workflows**: Alguns fluxos mais complexos demandaram pesquisa e testes

Apesar desses desafios, o sistema foi desenvolvido com sucesso e está funcional para casos de uso reais!

## 🎓 Desenvolvido para

Instituições de ensino, empresas de treinamento e organizações que necessitam emitir certificados em lote de forma profissional e automatizada.
