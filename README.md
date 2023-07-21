# Rust UI overview

This is *my* attempt at keeping an overview over all the UI related
libraries in Rust as I'm starting to make UIs using the language.

## A. Drawn by Rust code (via WebGL or WebGPU)

- [egui](https://github.com/emilk/egui): immediate mode (rerender the whole UI whenever anything changes), i.e. the simplest approach, but looks odd for larger UIs because it can't do fancy layouting due to the immediate mode approach, and may have scalability issues with very large UIs; has been around a while and probably won't go away

- [Iced](https://iced.rs/): reactive (Elm-like); seems pretty solid (recommended by people). For nicer UIs, if avoiding the DOM is fine, this may be the best bet.

## B. Drawn by non-Rust code (via WebGL or WebGPU)

- Flutter can be used from Rust; looks like one has to write Dart for the UI part though (also, the download is probably on the heavy side?)

## C. Drawn by the browser (DOM manipulation)

- [Sycamore](https://sycamore-rs.netlify.app/) (compile-time reactive / "signals based approach popularized by Solid JS")

- [Kobold](https://docs.rs/kobold/latest/kobold/) (compile-time reactive)

- [Yew](https://yew.rs/) (reactive); people have reported it to be relatively buggy (March 2023), and some examples feel slowish and/or buggy; see Sauron instead?

- [Sauron](https://github.com/ivanceras/sauron) (reactive): fork or reimplementation of Yew?

## D. Experimental frontier

I don't remember which ones would be able to work in the browser. You may not want to use these when concerned about long term stability.

- [Xilem](https://github.com/linebender/xilem): runtime reactive (Elm / SwiftUI inspired; replaces former Druid project)

    * [Xilem: an architecture for UI in Rust](https://raphlinus.github.io/rust/gui/2022/05/07/ui-architecture.html) ([Reddit](https://old.reddit.com/r/rust/comments/ukk1p4/xilem_an_architecture_for_ui_in_rust/), [HN](https://news.ycombinator.com/item?id=31297550))

- [A Proposal for an asynchronous Rust GUI framework](https://notgull.github.io/async-gui/) ([Reddit](https://old.reddit.com/r/rust/comments/13y3f3d/a_proposal_for_an_asynchronous_rust_gui_framework/))

## E. Local apps (not in the browser)

- Slint (Elm-like way to use Gtk; IIRC there were issues with this approach)
- [Tauri](https://tauri.app/): light-weight Electron replacement

## F. Others (I don't currently know anything about those)

- rui (inspired by SwiftUI, too early)
- [Makepad](https://github.com/makepad/makepad): too early
- Dioxus
- Draco
- Percy
- Seed
- Smithy

## G. Server-side, but could run the "server" part in WASM and use htmx

- [wasm-service](https://github.com/richardanaya/wasm-service)
- [Axum + Sqlite + minijinja + htmx winning website combo?](https://old.reddit.com/r/rust/comments/11gizhc/axum_sqlite_minijinja_htmx_winning_website_combo/)

