* TODO [2015-01-03 Sat] riap-app: Configurable prompt
* TODO [2015-01-03 Sat] riap-app: RIAP_HISTSIZE

  And also probably RIAP_HISTFILESIZE, RIAP_HISTIGNORE, RIAP_HISTTIMEFORMAT.
* TODO [2015-01-03 Sat] riap-app: Something like PATH? [#E]
* TODO [2014-12-28 Sun] riap-app: ctrl-c harusnya jangan langsung exit shell, tapi kembali ke prompt  :ux:
* BUG [2014-12-22 Sen] riap-app: muncul warning fail parse json (dari periga-argv) saat 'set output_format json'

  - mungkin per_arg_{json,yaml} bisa dimatikan di sini?
* BUG [2014-12-22 Sen] riap-app: setelah 'set output_format json', outputs jadi pada empty

  - ls, set, execute function semua hasilnya empty, cuma 'CMD --help' atau 'help'
    aja yang muncul outputnya (json diikuti dengan teks)
  - setelah dibalikin lagi 'set output_format text' barulah normal kembali
* TODO [2014-12-20 Sab] riap-app: make "file/dir" completion case-insensitive [#C]

  - agak ribet nih, sama seperti waktu kita support ci=1 di
    Complete::Util::complete_file, kita harus iterate level by level. but it's so
    convenient :)
  - log ::
    + [2014-12-28 Sun] gw udah buat Complete::Riap (berbasis Complete::Path) to
      make this simple, tapi ternyata agak ribet juga menggunakannya di riap-app
    + [2014-12-28 Sun] tapi kemaren gw menyadari, sekarang *udah* jadi
      case-insensitive, tanpa gw nyadar. kayaknya sejak Complete 0.06 (di mana
      setting ci, termasuk utk complete_array_elem, defaultnya ngikut ke setting
      $Complete::OPT_CI) dan defaultnya 1.
