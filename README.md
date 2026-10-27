# Tsunami simulator (tsunami) and window app — companion source for the book

Design documents and code for the tsunami simulator built in ***Toward a Million Lines XII — Building a Tsunami Simulator*** (Japanese title 『LLM で 100 万行のソフトウェア開発 XII — 津波のシミュレータをつくる』; the book is in Japanese).

`tsunami` (Python) computes a tsunami from its source to the shore in three stages with nested grids: the **Pacific crossing** of the 2011 Tohoku-oki tsunami, the **continental shelf and Ofunato Bay**, and **runup in the city of Ofunato**, with and without the breakwater. It also computes **Tonga-type tsunamis** raised by an atmospheric pressure wave (the Lamb wave and Proudman resonance) and analyses the **decay** of the wave outside the bay mouth. It fetches the terrain, source and observation data itself (GSI elevation tiles, ETOPO 2022, GEBCO 2025, the 2011 Tohoku data, J-EGG500) and writes 2-D and 3-D animations and figures. A Windows window app (Flutter, Japanese and English screens) runs it. **The window holds no simulation of its own.**

## Download

**The ready-to-run app and the source are on the [Releases](../../releases) page**, not in this repository. The release has four separate ZIPs:

| File | Contents |
|:---|:---|
| `tsunami_exe.zip` | The Windows window app, ready built (**Japanese screens**), with the simulator it runs and launchers for a data fetch and a very short calculation |
| `tsunami_exe_en.zip` | The same app (**English screens** by default) |
| `tsunami.zip` | Design documents (`docs/`, Japanese, L1-L4, the source; `docs_en/`, the complete set for English readers: L1-L3 translated into English, L4 the Japanese originals as is) in separate folders, the code (`src/tsunami/`, `app/`), the requirements specification, and empty databases (`ledger/`) |
| `tsunami_animations.zip` | The animations of the calculations of the book (the 2011 Tohoku tsunami in three stages, Ofunato Bay and city with and without the breakwater, two Tonga-type cases): 27 MP4 video files, 2-D maps and 3-D views |

The app needs Python 3.11 and numpy, scipy, numba, matplotlib, pillow and netCDF4 on your PC (see the README inside the ZIPs); extract to a short path. There is **no APK** (the app is a Windows desktop app). The app is **not code-signed**, so Windows may warn you. Data, computation results and tests are not included; the window fetches the data for you. The first run takes a few minutes (numba compiles); try the very short calculation first.

You are free to change the design documents and the code and compare the results.

---

## License

- **The author holds the copyright.**
- **The code is under the GNU General Public License v3.0 or later (GPL-3.0-or-later).** The full text is [`LICENSE`](LICENSE). **If you modify it and distribute it, you must publish the source under the same GPL-3.0-or-later terms.**
- **The design documents and the text are under the Creative Commons Attribution-ShareAlike 4.0 International license (CC BY-SA 4.0).** This covers `docs/`, `docs_en/`, the READMEs and the other written text of this repository, and the text of the matching book. See [`LICENSE-DOCS.md`](LICENSE-DOCS.md).
- **If you use them, say so.** State where it came from (the title of the book and the name of this repository) and keep the copyright notice. If you changed it, say that you changed it.
- **In this project the design documents are the source of the code.** When you publish something made from this code, **publish the design documents together with the code.**
- Third-party components (numpy, scipy, numba, matplotlib, pillow, netCDF4 installed by `pip install .`; the Flutter engine inside the EXEs) remain under their own original licenses.
- The rights to the input data (GSI elevation tiles; ETOPO 2022: NOAA NCEI; GEBCO 2025: GEBCO Compilation Group; the 2011 Tohoku data: MacInnes et al., GitHub `rjleveque/tohoku2011-paper1`; J-EGG500: JODC) stay with the providers. The data are not in this repository.
- Provided "as is", without warranty — as the GPL-3.0 text says. **This simulator is not a forecast or a warning of tsunamis; do not use it for decisions on disaster prevention.**

## 著作権とライセンス

- **著作権は、著者にあります。**
- **コードは、GNU General Public License v3.0 以降（GPL-3.0-or-later）です。**全文は [`LICENSE`](LICENSE) です。**改変して配布するときは、同じ GPL-3.0 以降の条件で、ソースを公開する義務があります。**
- **設計書と文章は、Creative Commons 表示-継承 4.0 国際（CC BY-SA 4.0）です。**このリポジトリの `docs/`・`docs_en/`・README ほかの文章と、対応する本の文章が当たります。内容は [`LICENSE-DOCS.md`](LICENSE-DOCS.md) です。
- **使ったときは、使ったことを書いてください。**どこから使ったか（本の題名と、このリポジトリの名前）と、著作権の表示を、使った先に書いてください。直したときは、直したことも書いてください。
- **このプロジェクトでは、設計書がコードの源です。**コードを使って作ったものを公開するときは、**設計書も、コードと一緒に公開してください。**
- 第三者の部品（`pip install .` で入る numpy・scipy・numba・matplotlib・pillow・netCDF4、EXE の中の Flutter の engine）は、それぞれの元のライセンスのままです。
- 入力に使うデータ（国土地理院の標高タイル、ETOPO 2022: NOAA NCEI、GEBCO 2025: GEBCO Compilation Group、2011 年東北沖のデータ: MacInnes ほか〔GitHub `rjleveque/tohoku2011-paper1`〕、J-EGG500: JODC）の権利は、提供元に残ります。データはこのリポジトリに含みません。
- 現状のまま（as is）提供します。保証はありません（GPL-3.0 の全文のとおりです）。**このシミュレータは、津波の予報でも警報でもありません。**防災の判断には使わないでください。
