## Q1
`garupa-1` という名前の namespace を作成し、その中に以下を満たす2つのPodを実行してください。

1. `gcr.io/ca-tominaga-test/simple-http-server` image を実行する `roselia-yukina` という名前の Pod

2. `gcr.io/ca-tominaga-test/alpine-spin:1.0.0` image と `nginx:1.7.9` image を実行する `roselia-risa` という名前のPod

## Q2
` garupa-2` という名前の namespace を作成し、その中で下記のものを作成してください。

1. 以下の2つのConfigmapを作成してください
- `localhost:4096` という value を持つ `CONNECTION_STRING` key
- `google.com` という value を持つ `EXTERNAL_URL` key

2. 1.で作成したConfigmapを環境変数として設定した `gcr.io/ca-tominaga-test/alpine-spin:1.0.0` image を実行する 任意の名前の Podを作成してください

## Q3
`failed-deployment.yaml` から Deployment リソースを作成し、失敗することを確認してください。
その後、エラーが発生しないようにファイルを編集して再度 Deployment リソースを作成してください。

## Q4
kubectlコマンドのみを使って `nginx:1.7.9` image を実行する5つのreplicaを持ったDeploymentを任意の名前で作成してください。
その後、NodePort typeのサービスを利用して、このDeploymentを外部に公開してください。
これらを実行した際のkubectlコマンドを記述してください。
(yamlファイルの使用は禁止です)

## Q5
まずは `yukina-pv` という名前の1GiBの容量を持つPersistentVolumeを作成してください。
このPersistentVolumeは hostPath typeであり、 ReadWriteOnce 属性を持つものとします。

その後、`yukina-pvc` という名前の PersitentVolumeClaim を作成してください。
このPVCは 512MiBをリクエストするものとします。

最後に、`yukina-pv` が コンテナ内部の `/etc/yukina-data` にマウントされるように `nginx:1.7.9` image を実行するPodを作成してください。
