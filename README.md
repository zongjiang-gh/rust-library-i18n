# Rust library translation (rust-src/rust-std/stdlib/rustlib translation)



[简体中文](./README_zh-CN.md)



This is the place to translate [Rust library](https://github.com/rust-lang/rust/tree/master/library), the relevant source code comes from <https://github.com/rust-lang/rust>.

Having a documentation in your native language is essential if you don't speak English, and still enjoyable even if you do. The Rust standard library is of high quality, no matter whether you are a novice or a veteran, you can benefit from it.

This repository contains all the source code files of the `rust-src` component, and structured translation of all its source codes, mainly including the translation of the Rust core library, the translation of the Rust standard library, and some other resources. The repository uses the [`Cmtor`](#) program and uses the `JSON` file to complete all translation work. When Rust is updated, it will automatically generate a localized translation for it within 10 days.



## goals


- 📦 Coverage

  The Rust library translation has supported the translation of all Rust documents in the `rust-src` source code

- 🔨 Refresh rate

  Be able to quickly discover the updates in the document and respond to it so that the document is always up-to-date and bid farewell to the problem of obsolete documents

- 🚄 Update frequency

  When Rust releases a new version, the Rust library translation will be updated within 10 days

- 🧰 Reuse rate

  It only needs to be translated once for repeated builds

- 💪 Support multi-person collaboration

  Use `JSON` format, simple and efficient, anyone can easily `PR`

- 💡 Smart tips that can be used for `IDE` tools

  Smart tips can help Rust developers quickly understand Rust `API` and improve the development efficiency and code quality of Rust engineers

- 🏳️‍🌈 Multi-language support, capable of generating documents in multiple languages

  Can build localized documents for each supported language, you can organize a translation team and submit `PR` to get support for other languages

- ✅ Automatically generated

  The Rust document is automatically generated by the `Cmtor` program without any manual intervention



## Language support

The Chinese version of the Rust standard library is currently supported. If you want to support other languages, you'd better form a translation team of more than 3 people, and the translation team will work together to complete the translation. If you don't have a translation team and you can't continue to submit PRs, then you'd better not submit `ISSUES`.



Supported languages：

- Rust Standard Library Chinese Version



In theory, it can support multiple languages：

- Rust標準ライブラリ日本語版
- Rust 표준 라이브러리 한국어 버전
- Version française de la bibliothèque standard Rust
- Rust Standard Library Deutsche Version
- Libreria standard Rust versione italiana
- Rust Biblioteca estándar de en español
- Rust Стандартная библиотека Русская версия
- ...



## How to download the translated Rust document

> The documents provided by this repository are mainly used for learning and communication. In order to make the project sustainable and healthy development, the translation of all documents will be completed with the help of translation engine and manual translation. Some minor errors will inevitably occur when using a translation engine. If your requirements are relatively high and you do not approve the translation engine or the quality of manual translation, please do not use any files in the repository. Please refrain from any impolite and meaningless discussions. If you think that the translation is not good, you can refuse to use it or submit a PR, but please do not use `ISSUES` to criticize or accuse it. This is very impolite behavior. Please focus the discussion on learning and communicating the Rust language itself, Thank you for your support and understanding.
>
> If you use the content contained in the repository, It means you agree to the above content.



Only supported languages are available for download, you can jump to the `dist` directory to download the latest build results.



## How to use Rust localized documents

> All localized documents in this repository will be updated with the update of Rust. When using localized documents, the localized document version and the Rust version must be consistent. And you cannot use the `nightly` version, but use the `stable` version.



If you are just starting to use Rust, after Rust is successfully installed, you should also install `rust-src` through the `rustup component add rust-src` command. After installing `rust-src`, please follow the steps below:

1. First get the value of the system environment variable `CARGO_HOME`, this value is a file path
2. Under the `CARGO_HOME` folder, find a folder named `.rustup`, and under the folder there is a folder named `toolchains`
3. In the `toolchains` folder, find the Rust version you are currently using and open it, for example, `stable-x86_64-pc-windows-msvc` on Windows
4. Then open the `lib/rustlib/src/rust` directory, the folder under this directory is where the source code of the Rust standard library is located
5. Save a copy of everything in the `lib/rustlib/src/rust/library` folder
6. Download the localized document source file corresponding to this repository, rename it to `library` and place it under the `lib/rustlib/src/rust` folder
7. Run: `rustup default stable` to switch to the `stable` version
8. Restart the `IDE` tool, and the smart prompt of the localized document starts to work
9. Happy coding！



## ~~Early preview files~~

`Rust` standard library localization documents have some early preview files, please jump to the [previews](https://github.com/wtklbm/rust-library-i18n/tree/main/previews) page to download them. Please note that these preview files have been deprecated and no more updates will be provided.

Before downloading, you need to know what the area code of your area is. For example, friends in China can download `zh-CN.zip` or `zh-TW.zip`, friends in Korea can download `ko.zip`, friends in Japan can download `ja.zip`, friends in Germany can download `de.zip`, and friends in Russia can download `ru.zip`.

For details, see：<https://cloud.google.com/translate/docs/languages>



## Translation rules

When translating Rust documents, please follow the following translation rules.

- Use honorific names when translating, for example, `you` should be translated into `您` instead of `你`
- Because there are no fixed translations for some inherent nouns, such nouns should not be translated
- Pay attention to the capitalization of proprietary words, such as `rust` should be written as `Rust`
- Chinese characters, letters, numbers, brackets, quotation marks, etc. are separated by a space, and the letters and numbers must be half-width symbols
- Avoid using internet language, abbreviations, and emotional vocabulary
- When translating Chinese, full-width Chinese punctuation should be used, and there should be no spaces between full-width punctuation and other characters
- That are wrapped in arbitrary parentheses and quotation marks should not be translated. such as：
  - \`thread\` in [\`thread\`]
  -  \`Copy\` in [\`Copy\`][#id]
  - ...
- ...



## Contributing

If you have plenty of spare time, love Rust and are learning Rust, and want to learn more about the core of Rust, then translating Rust documents is a good way to learn.

It should be noted that you cannot modify the files in the `dist` directory, but modify the files in the `src` directory. All translation files in this repository are in `.json` format, you can open them and give the correct translation, then `PR`, which is very simple for everyone.

Before submitting a PR, you need to familiarize yourself with the content in `.json`.In the `.json` file, each translation item has three attributes.

```javascript
{
    // Source content to be translated.
    // NOTE: You cannot modify it.
    "source": "This is a test.",

    // The translation given by the translation engine can be used as the final translation result or as a reference for the translator.
    // NOTE: You cannot modify it.
    "suggest": "这是一个测试。",

    // A string or a boolean value, this value is up to you to change.
    //
    // If it is a string：
    //  - If the string is not empty, it means that the value of the `translate` attribute is used as the translation result.
    //  - If it is an empty string, it means that no one has translated it yet.
    //
    // If it is a boolean：
    //  - If it is `true`, it means to accept the translation given by the translation engine and use it as the translation result.
    //  - If it is `false`, it means that the current content does not need to be translated.
    "translate": ""
},
```



### Examples

Trust the translation engine and use its value as the final translation：

```javascript
{
    "source": "This is a test.",
    "suggest": "这是一个测试。",
    "translate": true
}
```



Source content does not need to be translated：

```javascript
{
    "source": "Rust",
    "suggest": "锈",
    "translate": false
}
```



It`s up to you to translate and serve as the final translation result：

```javascript
{
    "source": "This is a test.",
    "suggest": "这是一个测验。",
    "translate": "这是一个测试。"
}
```



## License

MIT OR Apache-2.0



## connection

I love front-end and Rust, If you have any questions about localization, please feel free to contact me.

<div  align="center">
	<img src="./assets/wechat.png" align="left" width="47%" />
</div>



