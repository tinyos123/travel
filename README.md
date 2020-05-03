# Chaos

## Workshop
1. Inside one of the containers
```
docker exec -it app3 sh
```
add and run the command to fill the disk: `./fill_disk.sh /fill 2G`.

2. Kill the container and start it again. What happened?

3. Try to create a file inside another container.

4. What surprising fact did you learn?

## Reflection
How could you extend this workshop to collect more measures and devise an automated experiment to understand which event/failure causes the most problems?
