# asobibar-19-site

ASOBIBAR 神戸三宮店 満19歳プランLP の**配信用**リポジトリ。

**ここは編集しない。** ソースは `HIC-DigitalSolution/asobibar-19`（private）で、
このリポジトリはそこから**ブラウザに配るファイルだけ**を写したもの。

- 公開URL: https://hic-digitalsolution.github.io/asobibar-19-site/
- 中身: `index.html` / `css/style.css` / `img/*` / `video/*` のみ
- カンプ・Sass・作業ログ・harness は private 側にある

## 更新のしかた

private 側で作業してビルドまで済ませたあと、そこから写して push する。

```sh
SRC=<asobibar-19 のパス>
cp "$SRC/index.html" index.html
cp "$SRC/css/style.css" css/style.css
for f in asobibar-logo-dark.svg favicon.svg og-image.jpg \
         play-darts-sannomiya.jpg play-beerpong-sannomiya.jpg play-games-sannomiya.jpg; do
  cp "$SRC/img/$f" "img/$f"
done
cp "$SRC/video/karaoke-scene.mp4" "$SRC/video/karaoke-scene-poster.jpg" video/
git add -A && git commit -m "<何を変えたか>" && git push
```

**`css/style.css` は Sass の生成物。**private 側で `npm run build` を通してから写すこと。
