2025_07_16:13:59_JST
```
`commands/setup.py`
`wizard/ShoestringOperation.py`
以上の 2fileを差し替える事により、
① wizardの setup実行時には、nodeﾃﾞｨﾚｸﾄﾘが作成され、nodeﾃﾞｨﾚｸﾄﾘに node本体が格納される。
② wizardの upgrade実行時には、shoestring/rest_overrides.jsonが存在する場合には、`--rest-overrides shoestring/rest_overrides.json`が引数として命令に追加される。

③ commandの setup記述で、それぞれの引数に、ﾃﾞﾌｫﾙﾄ値を設定した。
これにより、以下に挙げる引数は、条件に合致する場合は省略可能とした。
また、引数にて該当する ﾌｧｲﾙの場所と名前を明示的に記述すると、記述された引数は適用される。

`--ca-key-path ca.key.pem`の場合は、`--ca-key-path`引数を省略可能。
`--config shoestring/shoestring.ini`の場合は、`--config`引数を省略可能。
`--overrides shoestring/overrides.ini`の場合は、`--overrides`引数を省略可能。
`--directory node`の場合は、`--directory`引数を省略可能。
※1 `--directory`引数で、存在しない ﾃﾞｨﾚｸﾄﾘを指定した場合は、引数で指定した場所と名前の ﾃﾞｨﾚｸﾄﾘが新規作成され、そこに node本体が格納される。
`--package mainnet`の場合は、`--package`引数を省略可能。
`--rest-overrides shoestring/rest_overrides.json`の場合は、`--rest-overrides`引数を省略可能。
※2 `--rest-overrides`引数を省略した場合で、`shoestring/rest_overrides.json`が存在する場合は、`--rest-overrides shoestring/rest_overrides.json`が引数となり、適用される。
※3 `--rest-overrides`引数を省略した場合で、`shoestring/rest_overrides.json`が存在しない場合は、`--rest_overrides`引数は適用されない。
```
```
`commands/setup.py`
`wizard/ShoestringOperation.py`
By replacing the above two files,

① When running wizard setup, the node directory is created and the node body is stored in the node directory.
② When running wizard upgrade, if shoestring/rest_overrides.json exists, `--rest-overrides shoestring/rest_overrides.json` is added as an argument to the command.

③ In the command setup description, a default value is set for each argument.
As a result, the arguments listed below can be omitted if the conditions are met.
Also, if the location and name of the corresponding file are explicitly stated in the argument, the stated argument will be applied.

In the case of `--ca-key-path ca.key.pem`, the `--ca-key-path` argument can be omitted.
If you use `--config shoestring/shoestring.ini`, you can omit the `--config` argument.
If you use `--overrides shoestring/overrides.ini`, you can omit the `--overrides` argument.
If you use `--directory node`, you can omit the `--directory` argument.
*1 If you specify a directory that does not exist with the `--directory` argument, a new directory with the location and name specified in the argument will be created, and the node body will be stored there.
If you use `--package mainnet`, you can omit the `--package` argument.
If you use `--rest-overrides shoestring/rest_overrides.json`, you can omit the `--rest-overrides` argument.
*2 If the `--rest-overrides` argument is omitted and `shoestring/rest_overrides.json` exists, `--rest-overrides shoestring/rest_overrides.json` will be the argument and will be applied.
*3 If the `--rest-overrides` argument is omitted and `shoestring/rest_overrides.json` does not exist, the `--rest_overrides` argument will not be applied.
```
