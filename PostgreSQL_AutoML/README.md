# PostgreSQL integration with AutoML

![](https://raw.githubusercontent.com/mljar/mljar-examples/master/media/PostgreSQL_AutoML_v2.png)

---

Article available on [MLJAR's blog](https://mljar.com/blog/postgresql-machine-learning/).

**`mljar-supervised`** autoML python package: https://github.com/mljar/mljar-supervised

---
Set up example database:
```
docker build -t mydb:latest .
docker run --name my_local_db -e POSTGRES_PASSWORD=1234 -e POSTGRES_DB=db -p 5555:5432 mydb:latest
```

Create table and insert training data:
```
python init_db.py
```

Train AutoML:
```
python train_automl.py
```

Compute predictions with AutoML and insert into the database:
```
python predict.py
```

Compute accuracy on live data samples:
```
python feedback.py
```

