```python
pip freeze > requirements.txt
```

Now to remove one by one

```python
pip uninstall -r requirements.txt
```

If we want to remove all at once then

```python
pip uninstall -r requirements.txt -y
```
