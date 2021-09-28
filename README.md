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
