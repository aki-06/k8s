## リソース作成/変更コマンド

```
kubectl apply -f <filename>
```

- オプション
    - -f filename: マニフェストファイルパス

## リソース確認コマンド

```
kubectl get [-f <filename>][TYPE]

# リソース全てを指定
kubectl get all
```

- オプション
    - -f filename: マニフェストファイルパス
    - TYPE: リソース種別

## リソース削除

```
kubectl delete [-f <filename>][TYPE][-o [wide|yaml]]
```

- オプション
    - -f filename: マニフェストファイルパス
    - TYPE/NAME: リソース種別/リソース名
    - -o [wide|yaml]: 出力形式を指定
        - wide: 追加情報の表示
        - yaml: yaml形式で表示

## コンテナへ入る

```
kubectl exec -it POD sh
```

- POD: pod名

## ファイル転送

```
# host→pod

kubectl cp <src> <pod-name>:<dest>
```

- src: 転送元ファイル名/フォルダ名
- pod-name: 転送先のpod名
- dest: 転送先フォルダ名/ファイル名

```
# pod→host

kubectl cp <pod-name>:<src> <dest>
```

- pod-name: 転送元のpod名
- src: 転送元ファイル名/フォルダ名
- dest: 転送先フォルダ名/ファイル名

## 状態(概況)確認

```
kubectl describe [TYPE/NAME]
```

- TYPE/NAME: リソース種別とリソース名

## ログ(詳細)確認

```
kubectl logs -f [TYPE/NAME][--tail=n]
```

- TYPE/NAME: リソース種別とリソース名
- --tail=n: 直近のnレコードだけ取得