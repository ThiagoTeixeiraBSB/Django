# E-commerce com Django

# Como rodar o projeto

- No terminal, execute o comando
```
docker-compose up --build
```

- Para rodar os testes:
```
docker-compose exec web pytest
# algumas opções:
docker-compose exec web pytest -x --cov --cov-report=html
```

- Não esqueça de rodar as migrations:
```
docker-compose exec web python manage.py migrate
```

- Se você não quiser procurar/criar fotos para os seus produtos, utilize a fixture `products.json`. As imagens também estão nesse repositório, na pasta media. Para inserir os produtos no banco de dados execute:
```
docker-compose exec web python manage.py loaddata products
```

- Não esqueça de criar um superuser para acessar a interface de admin:
```
docker-compose exec web python manage.py createsuperuser
```

- Uma outra opção interessante é executar esse comando para acessar o container:
```
docker-compose exec web bash
```

E a partir daí rodar os comandos normalmente, sem acrescentar `docker-compose exec web` na frente.

Por fim, acesse o site neste link: [http://localhost:8000/](http://localhost:8000/)
