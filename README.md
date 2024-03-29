All configurations and Zeppelin notebooks are persisted outside of the
image. To set up directories for mount volumes:

```bash
bash setup_dir.sh
```

Set up the Kafka infrastructure in Docker:

```bash
docker-compose -f ./docker-compose.yml up -d
```

Test the Kafka infrastructure:

```bash
python producer.py
```

Open another terminal and run:

```bash
python consumer.py
```

Start coding in Zeppelin running in the browser:

http://localhost:8080

Note: The artifact required to read from Kafka in Spark is included in
the Zeppelin config. There is no need to have a Spark cluster running
since a Spark interpreter is packaged with Zepplin.

To kill the containers:

```bash
docker-compose down --remove-orphans
```

Created on macOS High Sierra.
