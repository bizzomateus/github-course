# :dart: Git Course
[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)

> :triangular_flag_on_post: OBJETIVO: gerenciar e colaborar em projetos de forma eficaz.

O Git é um sistema de controle de versão distribuído que permite que várias pessoas colaborem em um projeto. Ele ajuda a rastrear as alterações feitas nos arquivos e facilita a colaboração e a fusão de código. O Git é amplamente utilizado no desenvolvimento de software e é essencial para gerenciar repositórios de código.

# Cicle
![GitLifecycle](https://user-images.githubusercontent.com/6115449/72635747-4f54cd00-393c-11ea-8067-a522695226df.png)

## Recursos

- [Documentação Oficial do Git](https://git-scm.com/doc): A documentação oficial fornece informações detalhadas sobre os comandos e conceitos do Git.
- [Tutorial Git da Atlassian](https://www.atlassian.com/git/tutorials): A Atlassian oferece um tutorial abrangente que aborda desde os conceitos básicos do Git até os fluxos de trabalho avançados.
- [Guias do GitHub](https://guides.github.com/): O GitHub oferece uma coleção de guias e tutoriais sobre o uso do Git e do GitHub para controle de versão e colaboração.
- [Git Cheat Sheet (Portuguese)](https://training.github.com/downloads/pt_BR/github-git-cheat-sheet.pdf): Página com comandos resumidos do git.
- [Visualizing Git](https://git-school.github.io/visualizing-git/#free-remote): Uma ferramenta da Git School para visualizar graficamente as operações git.
- [Simulador Git Quiz](https://linkedin-faq.github.io/skill-assessments-quizzes/quiz/git?question=3): Perguntas sobre git em inglês.

> [!TIP]
> [Atlanssian Advanced Git Articles](https://www.atlassian.com/git/tutorials/advanced-overview): It has advanced tutorials for git that are really worth looking into.

>[!IMPORTANT]
> [Wrinting readme tips](https://docs.github.com/en/get-started/writing-on-github): O primeiro documento acessado do git é o README, aprender a escrever é importante.

## Key Points
<details>
<summary>
    
#### 1. Compreendendo os conceitos básicos do Git
</summary>

    - Repositórios: Um repositório Git é onde seus arquivos e histórico de alterações são armazenados.
        Você pode criar um novo repositório ou clonar um existente.
    - Commits: Um commit é uma alteração feita em seus arquivos.
        Cada commit possui uma mensagem descritiva e um identificador único.
    - Branches: Uma branch é uma ramificação do seu código principal.
        Ela permite que você trabalhe em diferentes funcionalidades ou correções de bugs de forma isolada.
    - Merges: O merge é o processo de combinar as alterações de uma branch com outra,
        integrando-as ao código principal.
</details>
<details>
    <summary>
        
#### 2. Ramificação e mesclagem
</summary>
    
    - Criar uma nova branch: Use o comando `git branch nome-da-branch`
        para criar uma nova branch.
    - Alternar entre branches: Use o comando `git checkout nome-da-branch`
        para alternar entre branches.
    - Mesclar alterações de uma branch para outra: Use o comando `git merge nome-da-outra-branch`
        para mesclar as alterações de uma branch para outra.
</details>
<details>
    <summary>
    
#### 3. Reverta alterações
</summary>

    - Desfazer um commit: Use o comando `git revert hash-do-commit`
        para desfazer um commit específico, criando um novo commit que desfaz as alterações.
    - Desfazer uma série de commits: Use o comando `git revert hash-ultimo-commit..hash-primeiro-commit`
        para desfazer uma série de commits, criando novos commits que desfazem as alterações.
</details>
<details>
    <summary>
        
#### 4. Resolva conflitos de mesclagem
</summary>

    - Identifique conflitos: Durante o processo de mesclagem, o Git pode detectar conflitos em arquivos
        que foram modificados em ambas as branches. Esses conflitos precisam ser resolvidos manualmente.
    - Resolva conflitos manualmente: Abra os arquivos com conflitos e edite-os para resolver as diferenças.
        Depois de resolver, adicione os arquivos modificados usando o comando `git add` e faça um commit.
</details>

## :mage_man: Recursos avançados do Git
  ```code
  git rebase
  ```
Permite reorganizar o histórico de commits, movendo-os para uma nova base. Isso é útil para manter um histórico linear e ordenado. Aqui estão alguns exemplos práticos de como usar o comando:
<details open>
    <summary>

### 1. Reorganizando commits em uma branch
</summary>

````
- Suponha que você tenha uma branch chamada "feature" que contém vários commits e você deseja reorganizá-los antes de mesclá-los com a branch principal.
- Use o comando `git rebase -i HEAD~n`, onde `n` é o número de commits que deseja reorganizar.
- Isso abrirá um editor de texto com uma lista de commits. Você pode reorganizar a ordem dos commits, remover commits ou combinar commits em um único commit.
- Salve o arquivo e feche o editor de texto. O Git reorganizará os commits de acordo com as alterações feitas.
- Verifique o histórico de commits usando o comando `git log` para garantir que os commits foram reorganizados corretamente.
````
</details>
<details>
    <summary>
        
### 2. Resolvendo conflitos durante o rebase
</summary>

```
- Durante o processo de rebase, você pode encontrar conflitos quando o Git tenta aplicar os commits em uma nova base.
- O Git irá pausar o rebasing e indicar os arquivos com conflitos.
- Abra cada arquivo com conflito, resolva as diferenças manualmente e salve as alterações.
- Use o comando `git add` para marcar os arquivos como resolvidos.
- Continue o rebase usando o comando `git rebase --continue`.
- Se houver mais conflitos, repita o processo até que todos os conflitos sejam resolvidos.
```
</details>

>[!WARNING]
> Lembre de ter cuidado ao usar o comando `git rebase`, pois ele reescreve o histórico de commits. Certifique-se de entender completamente as consequências antes de executar o comando.

### :cherries: Cherry-pick
> O cherry-pick permite copiar um commit específico de uma branch para outra. Isso pode ser útil quando você deseja aplicar uma alteração específica em outra branch.

O comando `git cherry-pick` permite copiar um commit específico de uma branch para outra. Isso é útil quando você deseja aplicar uma alteração específica em outra branch.

Por exemplo, suponha que você tenha uma branch chamada "featureA" e outra branch chamada "featureB". Se você deseja aplicar um commit específico da branch "featureA" na branch "featureB", você pode usar o comando `git cherry-pick <hash-do-commit>`.

#### Exemplo prático

1. Identifique o hash do commit que você deseja copiar da branch "featureA".
2. Verifique se você está na branch "featureB" usando o comando `git checkout featureB`.
3. Use o comando `git cherry-pick <hash-do-commit>` para copiar o commit específico da branch "featureA" para a branch "featureB".
4. Verifique se as alterações foram aplicadas corretamente usando o comando `git log` ou visualizando os arquivos modificados.

>[!CAUTION]
> Lembrar de resolver conflitos de mesclagem que surgirem durante o processo de cherry-pick.
    

Praticar regularmente e trabalhar em projetos reais é essencial para ganhar experiência com o Git. Quanto mais você usar o Git, mais familiarizado e confortável se tornará com suas funcionalidades avançadas.
