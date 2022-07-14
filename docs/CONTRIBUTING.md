# Contribuição

Para contribuir com esse projeto, você primeiro tem que selecionar a aba de issues onde lá estará listado as tarefas que precisam de manutenção ou criação. Siga sempre os métodos e estrutura adotadas pelos proprietários do projeto, não fuja dos requisitos leve a padronização como regra principal.


Por favor, siga a politica de pull request e reports abaixo explicados. 

## Reporte de bugs 

Neste tópico você pode entender como irá funcionar a política de reporte de bugs, você precisa informar através de um relatório os seguintes pontos:

- Onde você achou os bugs seja na interface ou no código
- Explique o comportamento divergente, explicando o caminho com o máximo de detalhes possíveis
- Seja muito especifico, coloque todas as técnicas que voê usou para achar esse bug, divida o problema em tópicos e com palavras simples mas significativas que permitem que os demais contribuídos consigam entender e agir sobre o bug de maneira mais efetiva.
- Se souber como corrigir, faça um passo a passo explicando sua solução.


A seguir o modelo de como fazer um relatório de bug.

- Nome e Endereço de email.
- Nome do produto onde você achou o erro.
- Versão do produto onde foi encontrado o erro.
- Componente ou módulo onde o erro está.
- Plataforma de hardware, pois alguns comportamentos divergentes podem ser relacionados ao hardware que o usuário usa.
- Sistemas operacional, pois cada sistema operacional trabalha de forma diferente algumas politicas de enfileiramento e poder computacional.
- prioridade e severidade do bug, pois alguns bugs podem ser postergados a resolução, mas se o bug for maior do que o cosmético ou se for no núcleo principal do projeto, descreva e coloque os tipos de severidade (Blocker, Critical, Major, Minor, Trivial, Enhancement).

## Abertura de branches

Você pode usar os branches para experimentar com segurança as alterações no seu projeto. Os branches isolam seu trabalho de desenvolvimento de outros branches do repositório. Por exemplo, você poderia usar um branch para desenvolver um novo recurso ou corrigir um erro. 

Para isso a equipe desenvolveu um documento de [politicas de branch.](https://github.com/UnBArqDsw2022-1/2022.1_G4_FluxoAgil/blob/main/policies/branch_policy.md)


## Padrões de commits 

Como ultizaremos github que é  uma ferramenta que serve para controlar um projeto de software e as mudanças que ocorrem neste projeto ao longo do tempo, e o commit é a peça fundamental para isso. Um commit serve como um ponto de retorno no projeto, possibilitando que os contribuidores adicionem trexos de código no repositório virtual no github. 

Para que os commits sejam feitos de forma clara e padronizada a equipe desenvolveu uma [politica de commit.](https://github.com/UnBArqDsw2022-1/2022.1_G4_FluxoAgil/blob/main/policies/commit.md)

## Processo de pull requests 

Este é um dos passos mais importantes para um projeto então siga a risca todas as informações para que sua tarefa seja aceita.

- Conserte todos os problemas importantes da sua tarefa 

1. Sempre mantenha atualizado o README.md com os detalhes de mudanças e inclua se possível as variáveis de ambiente que você utilizou. Assim como expor as portas das aplicações tanto no docker quanto local e suas respectivas rotas de parâmetros. 
2. Coloque o número da versão e algum expemplo de requisição para facilitar 
3. Você pode fazer o merge quando dois ou mais revisores comentarem a aprovação.
4. siga todos os passos orientados no Template padrão do github.
5. Após submeter seu pull request verifique constantemente o status de verificação. 

Lembrasse que todos os requisitos da issue devem ser contemplados para que seu pull request seja aceito! 
