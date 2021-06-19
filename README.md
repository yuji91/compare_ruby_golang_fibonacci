# compare_ruby_golang_fibonacci

[Qiita: RubyからGoの関数をつかう](https://qiita.com/achm/items/679b3f3af2cf377f0f02) を参考。


## Rubyでの実行結果
```
$ time ruby fib.rb
102334155

real	0m19.115s
user	0m15.480s
sys	0m0.180s

2回目: 15.7s
3回目: 14.8s
```

## Golangでの実行結果
```
$ time go run fib.go
102334155

real	0m1.623s
user	0m1.048s
sys	0m0.365s

2回目: 1.8s
3回目: 1.7s
```

## 結果
Rubyで15秒かかる処理が2秒未満で完了した。

## Golang(build済)の実行結果
```
$ go build fib.go
time ./fib

102334155

real	0m0.776s
user	0m0.761s
sys	0m0.008s

2回目: 0.7s
3回目: 0.7s
```

## 結果
build済のファイルを実行すると1秒未満で完了した。
