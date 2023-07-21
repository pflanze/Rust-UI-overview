# Rust UI overview

This is *my* attempt at keeping an overview over all the UI related
libraries in Rust.


A. drawn by Rust code (via WebGL or WebGPU)

    - egui: immediate mode (rerender the whole UI whenever anything changes), i.e. the simplest approach, but looks odd for larger UIs because it can't do fancy layouting due to the immediate mode approach, and may have scalability issues with very large UIs; has been around a while and probably won't go away
    
    - Iced: reactive (Elm-like); seems pretty solid (recommended by people). For nicer UIs, if avoiding the DOM is fine, this may be the best bet.

B. drawn by non-Rust code (via WebGL or WebGPU)

    - Flutter can be used from Rust; looks like one has to write Dart for the UI part though (also, the download is probably on the heavy side?)

C. drawn by the browser (DOM manipulation)

    - Sycamore (compile-time reactive / "signals based approach popularized by Solid JS")

    - Kobold (compile-time reactive)

    - Yew (reactive); people have reported it to be relatively buggy (March 2023), and some examples feel slowish and/or buggy; see Sauron instead?

    - Sauron (reactive): fork or reimplementation of Yew?

D. experimental frontier; I don't remember which ones would be able to work in the browser, but you may not want to use these when concerned about long term stability

    - Xilem: runtime reactive ("Elm-like") (replaces former Druid project) https://raphlinus.github.io/rust/gui/2022/05/07/ui-architecture.html https://old.reddit.com/r/rust/comments/ukk1p4/xilem_an_architecture_for_ui_in_rust/ https://news.ycombinator.com/item?id=31297550

    - "A Proposal for an asynchronous Rust GUI framework" https://old.reddit.com/r/rust/comments/13y3f3d/a_proposal_for_an_asynchronous_rust_gui_framework/

E. Local apps (not in the browser)

    - Slint (Elm-like way to use Gtk; IIRC there were issues with this approach)
    - Tauri: light-weight Electron replacement

F. Others (I don't currently know anything about those)

    - rui (inspired by SwiftUI, too early)
    - Makepad (https://github.com/makepad/makepad): too early
    - Dioxus
    - Draco
    - Percy
    - Seed
    - Smithy

G. Server-side, but could run the "server" part in WASM and use htmx

    - https://github.com/richardanaya/wasm-service
    - https://old.reddit.com/r/rust/comments/11gizhc/axum_sqlite_minijinja_htmx_winning_website_combo/

