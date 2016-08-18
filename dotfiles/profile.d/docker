#!/bin/bash

alias d="docker"
alias di="docker images"
alias da="docker ps -a"

dimgr() {
  local _filter
  _filter="${1:-<none>}"

  docker images | awk '/'"$_filter"'/ { system("docker rmi -f "$3) }'
}

dcor() {
  local _filter
  _filter="${1:-Exited|Dead}"

  docker ps -a | awk '/'"$_filter"'/ { system("docker rm -f "$1) }'
}

dcos() {
  local _filter
  _filter="${1:?Must provide filter argument, otherwise all containers will be stopped}"

  docker ps -a | awk '/'"$_filter"'/ { system("docker stop "$1) }'
}

dcok() {
  local _filter
  _filter="${1:?Must provide filter argument, otherwise all containers will be killed}"

  docker ps -a | awk '/'"$_filter"'/ { system("docker kill "$1) }'
}

denter() {
  local _container_id _container_pid
  _container_id="${1:?First argument must be a container identifier}"
  shift
  _container_pid="$(docker inspect --format '{{.State.Pid}}' "$_container_id" 2>&-)"

  if [[ -n $_container_pid ]] && [[ $_container_pid != 0 ]]
  then
    docker exec -it "$_container_id" "$@"
  else
    echo "No container matching '$_container_id'"
  fi
}
