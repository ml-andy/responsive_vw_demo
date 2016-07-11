# 利用 vw 搭配sass 製作 Responsive Web
優點：
1.完全可用原本切桌機的方法來切Responsive或手機型 網頁
2.可不再為了方便切板而使用viewport固定寬，使用正統的device-width

@function getVW($aa) {
  @return ($aa / 640) * 100vw;
}
