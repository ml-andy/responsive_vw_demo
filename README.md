# 利用 vw 搭配scss 製作 Responsive Web
Demo: [https://ml-andy.github.io/responsive_vw_demo/demo.html][home]

# 優點：
1.完全可用原本切桌機的方法來切Responsive或手機型 網頁，不用再換算百分比或使用 img 撐高度

2.使用正統的device-width，可不再為了方便切板而使用viewport固定寬

# 缺點：
不支援IE8以下、android 4.3以下

# 方式：
	@function getVW($aa) {

		@return ($aa / 'psd-width') * 100vw;

	}

'$aa':任何在psd裡原本使用px的地方(包含文字大小)

'psd-width':設計給予的psd檔寬度


# 用法：
如要在 640px 的PSD尺寸下製作一個可以隨視窗等比例縮放的 250px * 150px 的div

	@function getVW($aa) {

		@return ($aa / 640) * 100vw;

	}


	div{

		width: getVW(250);

		height: getVW(150);

	}
