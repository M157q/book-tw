# 錯誤處理

Rust 對可靠性的注重也包含錯誤處理。錯誤是軟體開發中不可避免的一環，所以 Rust 有一些特色能夠處理發生錯誤的情形。在許多情況下，Rust 要求你要任知道可能出錯的地方，並在編譯前採取行動。這樣的要求能讓你的程式更穩定，確保你能發現錯誤並在程式碼發佈到生產環境前妥善處理它們！

Rust 將錯誤分成兩大類：**可復原的**（recoverable）和**不可復原的**（unrecoverable）錯誤。像是找不到檔案這種可復原的錯誤，回報問題給使用者並重試是很合理的。而不可復原的錯誤就會是程式錯誤的跡象，像是嘗試取得陣列結尾之後的位置。

許多語言不會區分這兩種錯誤，並以相同的方式處理，使用像是例外（exceptions）這樣統一的機制處理。Rust 沒有例外處理機制，取而代之的是它對可復原的錯誤提供 `Result<T, E>` 型別，對不可復原的錯誤使用 `panic!` 將程式停止執行。本章節會先介紹 `panic!` 再來討論 `Result<T, E>` 數值的回傳。除此之外，我們也將探討何時該從錯誤中復原，何時該選擇停止程式。
