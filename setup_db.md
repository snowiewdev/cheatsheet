## mySQL
Grant access to localhost for development
```
GRANT ALL PRIVILEGES ON *.* TO 'my_user'@'%';
```

## Local json server
In terminal, install json server globally to get data from .json file
```
npm install -g json-server
```

start json server:
```
json-server ./data/db.json --port 3001
```
