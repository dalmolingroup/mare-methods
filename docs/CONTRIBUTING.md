# Como Contribuir para o Projeto MaRe

Agradecemos imensamente seu interesse em contribuir com o Projeto MaRe!  
Sua ajuda é fundamental para o avanço da nossa pesquisa e para a qualidade da nossa documentação e ferramentas.

Existem várias maneiras de contribuir — desde a correção de erros de digitação até a adição de novos scripts de análise.

---

## Como começar?

- **Procure por *issues***: Verifique a seção de [Issues](https://github.com/dalmolingroup/mare-methods/issues) do nosso repositório para ver se há tarefas abertas ou discussões em andamento.
- **Sugira novas ideias**: Tem uma ideia para uma melhoria, novo conteúdo ou novo script? Abra uma nova *issue* para que possamos discuti-la.

---

## Contribuindo com Texto e Documentação

Você pode contribuir com melhorias na documentação diretamente pelo **site da documentação** (baseado em MkDocs)!  
Basta clicar no botão **com um lápis** no canto superior direito da página que deseja editar.  
Isso abrirá a interface do GitHub, onde você poderá propor alterações sem precisar clonar o repositório.

> Essa é a maneira mais rápida e simples de corrigir textos, adicionar informações ou melhorar descrições!

---

## Adicionando Novos Scripts

Se sua contribuição envolve um novo script de análise (em Bash, Python, R, etc.), siga estas diretrizes:

1. **Crie uma pasta**  
   Adicione seu script na pasta `scripts/` na raiz do repositório. Se a pasta não existir, por favor, crie-a.

2. **Documente seu script**  
   Inclua comentários claros explicando:
   - O que cada parte faz
   - Quais são as dependências
   - Como executá-lo

3. **Atualize a documentação**  
   Se o script estiver relacionado a alguma página específica (ex: `classificacao_taxonomica.md`), adicione uma referência e um exemplo de uso.

---

## Tutorial: Como fazer um Pull Request (PR)

Se você não está familiarizado com o Git e o GitHub, não se preocupe!  
Siga este guia passo a passo para enviar suas contribuições.

---

### Passo 1: Faça um "Fork" do Repositório

"Fork" é como criar uma cópia pessoal do projeto no seu próprio perfil do GitHub.

- Vá para a página principal do repositório:  
  https://github.com/dalmolingroup/mare-methods
- Clique no botão **"Fork"** no canto superior direito.  
  O GitHub criará uma cópia do repositório na sua conta.

---

### Passo 2: Clone o seu Fork para a sua Máquina Local

Agora, você precisa baixar o repositório para o seu computador.

- No seu fork no GitHub, clique no botão verde **"< > Code"**
- Copie a URL (HTTPS é o mais fácil)
- No terminal, execute:

```bash
git clone https://github.com/SEU-USUARIO/mare-methods.git
cd mare-methods
```

---

### Passo 3: Crie uma Nova "Branch"

É uma boa prática criar uma *branch* separada para cada contribuição.

```bash
git checkout -b minha-nova-contribuicao
# Exemplo:
git checkout -b feature/adiciona-script-de-qc
```

---

### Passo 4: Faça suas Alterações

Edite os arquivos em seu editor favorito.  
Adicione scripts na pasta `scripts/`, corrija textos, etc.

---

### Passo 5: Salve suas Alterações (Commit)

Adicione os arquivos modificados ao *stage*:

```bash
# Adicionar um arquivo específico
git add scripts/meu_novo_script.py

# Ou adicionar tudo
git add .
```

Faça o *commit* com uma mensagem descritiva:

```bash
git commit -m "feat: Adiciona script para controle de qualidade com fastp"
```

> Dica: use prefixos como `feat:`, `fix:`, `docs:` para categorizar mudanças.

---

### Passo 6: Envie suas Alterações para o seu Fork (Push)

```bash
git push origin minha-nova-contribuicao
```

---

### Passo 7: Abra um Pull Request

Este é o passo final!

- Vá para o seu fork no GitHub
- O GitHub mostrará o botão **"Compare & pull request"**
- Se não aparecer, vá na aba **"Pull Requests"** > **"New pull request"**
- Base repository: `dalmolingroup/mare-methods`  
  Head repository: seu fork + sua branch
- Escreva um título e uma descrição clara
- Clique em **"Create pull request"**

---

Pronto!  
Os mantenedores do projeto revisarão sua contribuição.  
Eles podem pedir mudanças ou aceitar e fazer o *merge* do seu PR.

**Obrigado por contribuir! 🙌**

