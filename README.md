# 利用 vw 搭配scss 製作 Responsive Web
Demo: https://ml-andy.github.io/responsive_vw_demo/demo.html

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
如要在 640px 的PSD尺寸下製作一個可以隨視窗等比例縮放的 250px * 150px Div區塊

	@function getVW($aa) {

		@return ($aa / 640) * 100vw;

	}


	div{

		width: getVW(250);

		height: getVW(150);

	}

# 搭配自己的mixin 更有效率：
可以省去打function名稱的時間，同時做其他設定。
如要在 640px 的PSD尺寸下製作一個可以隨視窗等比例縮放並置中的 250px * 150px Div區塊

	@function getVW($aa) {

		@return ($aa / 640) * 100vw;

	}

	@mixin alt($wt:100%,$ht:100%,$left:0,$top:0,$mleft:0,$mtop:0){
		position:absolute;
		width:getVW($wt);
		height: getVW($ht);  
		top: $top;
		left:$left;
		margin-left:getVW($mleft);
		margin-top: getVW($mtop);
	}

	div{
		@include altvw(250,150,50%,50%,-125,-75);
	}