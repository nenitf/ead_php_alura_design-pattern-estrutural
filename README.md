# ead_php_alura_design-pattern-estrutural

> Projeto referente a [este](https://cursos.alura.com.br/course/php-design-pattern-estrutural) curso.

1. Crie o ambiente
```sh
docker-compose up -d
```
> Caso queira, ao final da configuração, pare o Docker com ``docker-compose down``

2. Crie o autoloader
```sh
docker-compose exec app composer du
```

## Execução

- Caso recém tenha feito a **configuração inicial** e o ambiente continue rodando, tudo certo. Pode acessar ``localhost:8989/arquivo-script.php``
- Do contrário, suba o ambiente novamente:
```sh
docker-compose up
```
> Pare com <kbd>Ctrl</kbd><kbd>C</kbd>

> Caso modifique Dockerfile, rebuilde com ``docker-compose up --build``

> Para acessar o container use ``docker-compose exec app bash`` ou execute os scripts diretamente pelo Docker ``docker-compose exec app php public/arquivo-script.php``

## Anotações

Padrões estruturais tratam de montar objetos e classes em estruturas maiores, mas mantendo isso flexível, extensível e principalmente manutenível.

---

- **Adapter** classe que adapta um detalhe de infra (envio de email, acesso de api e etc)
    > Adapter vs Facade: Adaptar vs Simplificar
- **Bridge** classe "intermediária" entre um recurso e um *adapter*, servindo como "tradutor" ou adaptando o recurso para o adapter. Esse padrão aumenta a extensibilidade do código
- **Decorator** injeta ou não funcionalidade a mais no construtor da classe. Semelhante a um "plugin"
- **Composite** torna mais simples percorrer arvore de objetos com uma interface comum, pois cada objeto fica responsável por saber contar/entregar algo a quem percorre
- **Facade** simplifica um módulo ou parte do sistema complexo para apenas um método
    > Uma classe de fachada, contendo apenas a funcionalidade desejada, pode ser bastante útil para autenticação, acesso a sistema de arquivos, cache, etc.
- **Proxy** "imita" uma classe envolvendo algum método dentro de outro método de mesma assinatura e realizando alguma operação, podendo chamar o método original ou não
    > Legal para cache, lazy loading e middlewares
- **Flyweight** focado em melhorar performance, separa trechos do código que podem ser reutilizáveis para poupar memória. Pode prejudicar o entendimento do código já que a classe se torna menos "semântica" e mais "útil"
