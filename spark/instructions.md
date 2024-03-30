# Start spark container
docker-compose up -d

# Copy file to spark cluster
docker cp -L spark_demo.py spark-spark-1:/opt/bitnami/spark/spark_demo.py

# Find spark cluster with
docker logs spark

# Execute pyspark file
docker-compose exec spark-spark-1 spark-submit --master spark://09c0c93c61bf:7077 spark_demo.py
