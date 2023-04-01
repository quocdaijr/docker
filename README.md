# LIST DOCKER IMAGES

### How to push image to dockerhub after built?
```
    docker-compose build --no-cache # build list images in file docker-compose.yml
    docker images # check list built images
    docker login # login dockerhub, enter username and password to login
    docker tag `image_id` `image_name_on_dockerhub`:`tag` # add tag for image, Ex: docker tag 35f914b19756 quocdaijr/php-fpm:8.1
    docker push `image_name_on_dockerhub`:`tag` # push image, Ex: docker push quocdaijr/php-fpm:8.0
```