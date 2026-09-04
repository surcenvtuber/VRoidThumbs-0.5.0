# VRoidThumbs-0.5.0
Windows Explorer thumbnails for .vroid / .vroidcustomitem / .vrm / .xwear / .xavatar
日本語 / English / 中文 / 한국어

日本語
概要
以下のファイルのサムネイルを Windows エクスプローラーに表示します。
.vroid / .vroidcustomitem ファイル内蔵のサムネイル
.vrm VRM meta のサムネイル（0.x / 1.0 両対応）
.xwear / .xavatar サムネイルを持たない形式のため、ファイル内で
最大のテクスチャを代わりに使用します。衣装の
アトラスなら色違いの判別に十分役立ちます。

使える画像が無いファイルは既定のアイコンに静かに戻ります。

使い方
1. VRoidThumbsSetup.exe を実行
2.「インストール」をクリック（「エクスプローラーを再起動して
サムネイルキャッシュを消去」はチェックしたままを推奨）
3. VRoid ファイルのフォルダーを開き、中アイコン以上の表示に切り替え

アンインストール
VRoidThumbsSetup.exe を再度実行し「アンインストール」をクリック。
レジストリは完全に元に戻ります。
コマンドライン: VRoidThumbsSetup.exe /uninstall

フォルダーが重くなりませんか
なりません。どちらのファイルも ZIP コンテナで、小さなプレビュー画像
(thumbnails/thumbnail.png / .jpg) が最初から入っています。本ツールは
ZIP のディレクトリを読んでその画像を取り出すだけで、モデルデータは
一切解析しません。150 MB のテストファイルで平均 1 ミリ秒未満でした。
Windows 側でもサムネイルはキャッシュされます。
（PSD 用パッチが重いのは、数百 MB のレイヤー画像を合成する必要が
あるためで、状況がまったく異なります。）

セキュリティ警告について
インストーラーはコード署名をしていないため、SmartScreen が
「発行元不明」と表示することがあります。「詳細情報」→「実行」で
進めてください。ソースコードは src/ に同梱しています。

既知の制限
- 64 ビット版 Windows のみ対応
- 現在のユーザーのみ (HKCU)。管理者権限は不要です
- サムネイルが無いファイルや破損ファイルは、既定のアイコンに
静かにフォールバックします
- インストール／アンインストール時に DLL が使用中だった場合、
次回の再起動時に自動的に削除されます

免責事項
pixiv / VRoid 公式とは関係のない非公式ツールです。
ファイルの読み取りのみを行い、.vroid / .vroidcustomitem を
書き換えることはありません。

English
What it does
Shows previews directly in Windows Explorer for:
.vroid / .vroidcustomitem - the thumbnail baked into the file
.vrm - the VRM meta thumbnail (VRM 0.x and 1.0)
.xwear / .xavatar - these formats carry no thumbnail, so the
largest texture in the file is used instead.
Works well for garment atlases (you can tell
colourways apart at a glance); less useful
for plain or unusual UV layouts.

Files with no usable image silently fall back to the default icon.

How to use
1. Run VRoidThumbsSetup.exe
2. Click "Install" (keep the "Restart Explorer and clear the thumbnail
cache" box ticked)
3. Open a folder with VRoid files and switch to medium or large icons

Removing it
Run VRoidThumbsSetup.exe again and click "Uninstall". All registry
entries are removed. Command line: VRoidThumbsSetup.exe /uninstall

Will it slow my folders down?
No. Both file types are ZIP containers with a small preview image
already baked in (thumbnails/thumbnail.png / .jpg). This tool seeks to
the ZIP directory, pulls out that one small image, and stops - it never
parses model data. On a 150 MB test container, extraction averaged
under 1 millisecond. Windows also caches thumbnails, so only the first
visit to a folder does any work.
(PSD thumbnail patches are slow because they must composite a
multi-hundred-megabyte layered image. This is a different situation.)

About the security warning
The installer is not code-signed, so SmartScreen may show an "unknown
publisher" prompt. Click "More info" -> "Run anyway". Full source is in
src/ if you would rather build it yourself.

Known limitations
- 64-bit Windows only
- Installs for the current user (HKCU); no administrator rights needed
- Files with no embedded thumbnail, or damaged files, silently fall
back to the default icon
- If the DLL is locked by Explorer during install/uninstall, the stale
copy is cleaned up on the next reboot

Disclaimer
Not affiliated with pixiv / VRoid. Read-only: it never modifies your
.vroid or .vroidcustomitem files.

中文
这是什么
让 Windows 资源管理器直接显示这些文件的预览图，不用再靠文件名猜：
.vroid / .vroidcustomitem —— 用文件自带的缩略图
.vrm —— 用 VRM meta 里的缩略图（VRM 0.x 与 1.0 都支持）
.xwear / .xavatar —— 这两种格式里没有缩略图，改用文件里最大的
那张贴图。对成衣类贴图效果很好，能一眼分出
同款的不同配色；纯色或异形 UV 的可能不好认。

没有可用图片的文件会安静地退回默认图标，不会报错。

怎么用
1. 双击 VRoidThumbsSetup.exe
2. 点「安装」（建议保留「重启资源管理器并清理缩略图缓存」的勾选）
3. 打开放 VRoid 文件的文件夹，视图切成「中等图标」或更大

不用了怎么办
再次运行 VRoidThumbsSetup.exe，点「卸载」。注册表会完全还原。
也可以命令行：VRoidThumbsSetup.exe /uninstall

会不会拖慢文件夹？
不会。这两种文件本身就是 zip 包，里面已经存好一张现成的小预览图
(thumbnails/thumbnail.png / .jpg)。本工具只跳到文件尾部读一下目录、
取出那张小图，不解析模型数据。在 150 MB 的测试档上，取图平均耗时
不到 1 毫秒。而且 Windows 会把缩略图缓存起来，同一个文件夹只算第一次。
（PSD 补丁之所以卡，是因为它必须把几百 MB 的分层大图解成合成图，
和这里的情况完全不同。）

关于安全提示
安装程序没有做代码签名，Windows SmartScreen 可能会弹「未知发布者」。
点「更多信息」→「仍要运行」即可。源码在 src/ 里，可以自己编译核对。

已知限制
- 仅支持 64 位 Windows（Win10 / Win11 实测环境为主）
- 只装给当前用户（HKCU），不需要管理员权限，也不会影响其他账户
- 文件里没有缩略图、或文件损坏时，会安静地退回默认图标，不会报错
- 安装/卸载时如果 DLL 正被资源管理器占用，会在下次重启时自动清掉

免责
本工具与 pixiv / VRoid 官方无关，是第三方工具。
它只读取文件，不会修改你的 .vroid / .vroidcustomitem。

한국어
소개
다음 파일의 미리보기를 Windows 탐색기에 표시합니다.
.vroid / .vroidcustomitem 파일에 내장된 썸네일
.vrm VRM meta 썸네일 (0.x / 1.0 모두 지원)
.xwear / .xavatar 썸네일이 없는 형식이라 파일에서 가장 큰
텍스처를 대신 사용합니다. 의상 아틀라스라면
색상 변형을 구분하기에 충분합니다.

사용할 이미지가 없으면 조용히 기본 아이콘으로 돌아갑니다.

사용 방법
1. VRoidThumbsSetup.exe 실행
2. "설치" 클릭 ("탐색기를 다시 시작하고 썸네일 캐시 삭제" 옵션은
켜 두는 것을 권장합니다)
3. VRoid 파일이 있는 폴더를 열고 보통 아이콘 이상으로 전환

제거 방법
VRoidThumbsSetup.exe를 다시 실행하고 "제거"를 클릭하세요.
레지스트리가 완전히 복원됩니다.
명령줄: VRoidThumbsSetup.exe /uninstall

폴더가 느려지나요?
아닙니다. 두 형식 모두 ZIP 컨테이너이며 작은 미리보기 이미지
(thumbnails/thumbnail.png / .jpg)가 이미 들어 있습니다. 이 도구는
ZIP 디렉터리를 읽어 그 이미지만 꺼낼 뿐, 모델 데이터를 분석하지
않습니다. 150 MB 테스트 파일에서 평균 1밀리초 미만이었습니다.
Windows도 썸네일을 캐시합니다.
(PSD 패치가 느린 이유는 수백 MB의 레이어 이미지를 합성해야 하기
때문이며, 여기와는 상황이 다릅니다.)

보안 경고 안내
설치 프로그램에 코드 서명이 없어 SmartScreen이 "알 수 없는 게시자"
경고를 표시할 수 있습니다. "추가 정보" → "실행"을 누르세요.
소스 코드는 src/ 폴더에 포함되어 있습니다.

알려진 제한
- 64비트 Windows만 지원
- 현재 사용자(HKCU)에만 설치되며 관리자 권한이 필요 없습니다
- 썸네일이 없거나 손상된 파일은 조용히 기본 아이콘으로 표시됩니다
- 설치/제거 시 DLL이 사용 중이면 다음 재부팅 때 자동 정리됩니다

면책
pixiv / VRoid 공식과 무관한 비공식 도구입니다.
파일을 읽기만 하며 .vroid / .vroidcustomitem을 수정하지 않습니다.
