# appmonitor-pipeline

![CI Status](https://img.shields.io/github/actions/workflow/status/Eduardo-Kolberg/appmonitor-pipeline/ci.yml?branch=main&label=CI&logo=github)

# Papel do Git na entrega contínua e a importância de branches e tags
O Git é utilizado para controle e versionamento de código, a importância dele para a entrega contínua é grande uma vez que permite que, atraves de branchs, diversos desenvolvedores trabalhem no mesmo projeto em requisitos diferentes com segurança sem modificar o código "principal" que está contido na branch main, juntando os códigos atraves de pull requests quando a feature nova estiver implementada ou o bug corrigido. Ademais o sistema de commits e branchs facilitam o rollback caso ele seja necessário. 
As tags também entram na parte de facilitadores de identificação de releases importantes, normalmente os que são promovidos para produção ou versões "major" ou seja que mudem algo significativo no projeto. Elas marcam pontos importantes e com isso tornam mais facil o rollback para esse ponto caso seja necessário, são úteis para ter um histórico dos releases da aplicação, ademais pode se usar o release e criação de tags para dar trigger no deploy para produção se utilizando do CI/CD.

# Diferenças entre cada tipo e contexto de variável
Temos três tipos de variáveis, env, vars e secrets. Env é a variável que é definida em nível de ambiente e utéis para atribuir valores que vão ser reutilizados dentro do escopo que ela foi declarada (nível workflow, step e job). Já o vars possuí escopo global uma vez que é uma variável de repositório, ela é acessada através do vars.nome_da_variável, é utilizado para valores que podem ser exibidos e compartilhados como no caso em tela onde botamos o ambiente e o e-mail de suport, elas não são criptografadas. Por fim temos os secrets, outra variável de nível de repositório, portanto global, que guarda informações não compartilháveis e de maneira criptografada, como podemos ver no action executado nesse projeto quando tentamos imprimir no log o seu valor não conseguimos (Pegamos um bug em aula onde vimos que isso é feito através de um "like" então tem situações onde é possível mostrar algum valor como em operações matemáticas que modifiquem o valor).

# Explique como logs e summaries ajudam a depurar pipelines
São por meio dos logs que podemos ver o que está acontecendo com os comandos da pipeline, se executaram corretamente, bem como os eventuais erros gerados, ou seja, os logs são extremamente importante para depurar pipelines. Já os summaries são um resumo do que aconteceu, contem informações importantes para sabermos onde foi rodado, quem iniciou e se tudo deu certo, poupando tempo de ter que procurar todas essas informações nos logs.

