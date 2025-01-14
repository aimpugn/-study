# prune

- [prune](#prune)
    - [docker prune?](#docker-prune)
    - [컨테이너](#컨테이너)
    - [이미지](#이미지)
    - [볼륨](#볼륨)
    - [네트워크](#네트워크)
    - [전체](#전체)
    - [연관된 명령어들](#연관된-명령어들)

## docker prune?

Docker에서 `prune` 명령어는 사용되지 않는 또는 불필요한 Docker 객체를 제거하는 데 사용되어 시스템의 청소와 공간 확보를 돕습니다. 다양한 리소스에 대해 다음과 같은 특정 `prune` 명령어가 있습니다:

- **컨테이너**: `docker container prune`는 모든 중지된 컨테이너를 삭제합니다.
- **이미지**: `docker image prune`는 사용되지 않는 모든 이미지를 삭제합니다. `-a` 옵션을 추가하면, 태그가 없는 모든 이미지도 삭제합니다.
- **볼륨**: `docker volume prune`은 사용 중이지 않은 모든 볼륨을 삭제합니다.
- **네트워크**: `docker network prune`는 사용 중이지 않은 네트워크를 삭제합니다.
- **전체 시스템**: `docker system prune`는 중지된 컨테이너, 미사용 이미지 및 볼륨을 포함하여 미사용 리소스를 일괄 삭제합니다. `-a` 옵션을 추가하면, 모든 미사용 이미지와 볼륨도 삭제됩니다.

`prune` 명령어 사용시 몇 가지 주의할 점이 있습니다:

1. **데이터 손실**

    `prune` 명령어는 사용하지 않는 리소스를 삭제하지만, 실수로 필요한 데이터를 삭제할 위험이 있습니다.
    특히 볼륨이나 네트워크 설정을 제거할 때 중요한 데이터나 설정이 포함되어 있지 않은지 확인해야 합니다.

2. **시스템 성능**

    대량의 데이터를 삭제할 때는 Docker의 성능에 잠시 영향을 줄 수 있습니다.
    따라서 운영 환경에서는 사용량이 낮은 시간에 `prune` 명령어를 실행하는 것이 좋습니다.

이러한 `prune` 명령어들을 사용하여 Docker 환경을 효과적으로 관리하고 시스템 리소스를 최적화할 수 있습니다.
항상 중요한 데이터가 백업되었는지 확인하고, 필요한 경우 특정 리소스만 선택적으로 삭제하는 방법을 고려하는 것이 좋습니다.

## 컨테이너

```bash
docker container prune
```

이 명령어는 모든 중지된 컨테이너를 제거합니다.
Docker에서 컨테이너를 실행하고 중지하면, 컨테이너는 시스템에 여전히 존재하지만 활성 상태가 아닙니다.
이러한 중지된 컨테이너들은 여전히 시스템 자원을 차지할 수 있으므로, `docker container prune` 명령어를 사용하여 이들을 일괄적으로 삭제할 수 있습니다.

사용자의 확인을 요구하며, 이를 통해 예상치 못한 데이터 손실을 방지할 수 있습니다.

## 이미지

```bash
docker image prune -a
```

이 명령어는 사용하지 않는 모든 Docker 이미지를 제거합니다.
`-a` 옵션은 "all"을 의미하며, 태그가 없거나, Dockerfile에서 더 이상 참조되지 않는 이미지를 포함하여 모든 사용하지 않는 이미지를 삭제합니다.
이는 많은 디스크 공간을 확보할 수 있지만, 필요할 때 이미지를 다시 다운로드해야 할 수도 있음을 의미합니다.

## 볼륨

```bash
docker volume prune
```

이 명령어는 사용하지 않는 모든 Docker 볼륨을 제거합니다.
볼륨은 컨테이너가 삭제되어도 데이터를 유지할 수 있는 영구적인 데이터 저장 영역입니다.
하지만 연결되지 않은 볼륨은 불필요한 데이터를 계속 저장하게 되므로, 이 명령을 통해 연결되지 않은 모든 볼륨을 삭제하여 공간을 확보할 수 있습니다.

## 네트워크

```bash
docker network prune
```

이 명령어는 사용하지 않는 모든 Docker 네트워크를 제거합니다.
Docker 네트워크는 컨테이너들이 서로 통신할 수 있도록 하는 가상의 네트워크 인터페이스입니다.
컨테이너가 더 이상 사용되지 않을 때, 이와 연결된 네트워크도 종종 필요 없게 됩니다.
`docker network prune`을 실행하면, 아무런 컨테이너도 연결되어 있지 않은 네트워크를 삭제하여 네트워크 구성을 깔끔하게 유지할 수 있습니다.

## 전체

```bash
docker system prune -a
```

이 명령어는 Docker 시스템 내의 사용하지 않는 모든 리소스를 종합적으로 정리합니다.
`-a` 옵션을 포함하면, 중지된 컨테이너, 사용하지 않는 네트워크, 볼륨, 그리고 모든 이미지(연결된 컨테이너가 없는 경우)를 제거합니다.
이 명령은 특히 디스크 공간을 대폭적으로 확보해야 할 때 유용하며, Docker 환경을 최적화하는 데 매우 효과적입니다.

## 연관된 명령어들

`prune`과 관련된 다른 Docker 명령어로는 다음과 같은 것들이 있습니다:

- **`docker rm`**

    특정 컨테이너를 제거합니다.
    `prune`과 비교하면, `docker rm`은 특정 대상을 명시적으로 지정하여 삭제하는 반면, `prune`은 조건에 맞는 대상을 일괄적으로 삭제합니다.

- **`docker rmi`**

    특정 이미지를 제거합니다.
    이는 `docker image prune`과 유사한데, `rmi`는 특정 이미지를 직접 지정하여 삭제하는 반면, `prune`은 더 넓은 범위의 이미지를 조건에 따라 삭제합니다.

- **`docker system df`**

    Docker가 사용하는 디스크 공간을 보여줍니다.
    이 명령어는 얼마나 많은 리소스가 사용되고 있는지를 확인한 후 `prune`을 실행하여 공간을 확보할 때 유용합니다.
