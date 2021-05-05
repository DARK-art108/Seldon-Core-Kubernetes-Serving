# **Sentiment Analysis**

---

#### Build

```
$ s2i build . seldonio/seldon-core-s2i-python3:0.12 ritesh2000/sentiment-analysis:0.1.0
$ docker push ritesh2000/sentiment-analysis:0.1.0
```

#### Test

```
$ docker run --name "sentiment-analysis" --rm ritesh2000/sentiment-analysis:0.1.0
$ docker exec -it sentiment-analysis python SentimentAnalysis_Test.py
```

#### Usage

```
$ docker run --name "sentiment-analysis" --rm -p 5001:5000 ritesh2000/sentiment-analysis:0.1.0
$ curl -g http://localhost:5001/predict --data-urlencode 'json={"data": {"names": ["message"], "ndarray": ["All too much of the man-made is ugly, inefficient, depressing chaos."]}}'
```
