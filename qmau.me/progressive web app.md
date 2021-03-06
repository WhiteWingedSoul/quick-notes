Trong một tối bookmark dạo trên medium mình có đọc được [iOS đã hỗ trợ Progressive web apps(PWA) trong bản cập nhật mới nhất](https://medium.com/@firt/progressive-web-apps-on-ios-are-here-d00430dee3a7).  Mình biết đến PWA qua phần trình bày của anh [Trung Dinh Quang](https://developers.google.com/experts/people/trung-inh-quang?hl=vi) tại Google Devfest 2016. Không biết có phải do phần trình bày bằng giọng Huế đặc trưng của anh không mà mình cực kỳ ấn tượng với khái niệm mới này. Lúc đó PWA là một công nghệ mới dựa được viết bằng javascript được một vài kỹ sư của google phát triển và mới chỉ có android hỗ trợ, bây giờ có thiết bị để test rồi, tiếp tục get my hands dirty thôi =))

![size-reach](https://qmau.me/uploads/mzakDKScRb4eO4TP.png)


## Progressive web apps
### What the heck?
[Theo google](https://developers.google.com/web/progressive-web-apps/), progressive web apps là những ứng dụng web giúp người dùng có những trải nghiệm sau:
- [Tin cậy](https://developers.google.com/web/progressive-web-apps/checklist): Ứng dụng chạy ngay sau khi khởi động bất kể trạng thái kết nối mạng của thiết bị. Một service nhỏ hoạt động như một proxy phía client và bộ nhớ cache sẽ giúp ứng dụng trở nên tin cậy, người dùng có thể sử dụng bất cứ lúc nào, không phụ thuộc vào Internet.

- [Nhanh](https://developers.google.com/web/fundamentals/performance/why-performance-matters/) **53%** người dùng sẽ không truy cập site nếu thời gian load quá **3s** và khi trang được load, người dùng muốn có một ứng dụng có thể tương tác được ngay.

- [Gắn kết](https://developers.google.com/web/fundamentals/web-app-manifest/) Người dùng có thể cài đặt app trên home screen và sử dụng ở chế độ fullscreen, thông qua việc sử dụng web manifest. Có hỗ trợ [push notification](https://developers.google.com/web/fundamentals/push-notifications/) với các thiết bị di động (chưa được hỗ trợ trên iOS 🤔)


<iframe width="560" height="315" src="https://www.youtube.com/embed/Shu6_lO1PW8?start=4377" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>


Mình vẫn chưa bao giờ hết bất ngờ với khả năng sáng tạo của Steve Jobs. Tại WWDC2007 cách đây **11 năm**, ông đã giới thiệu về một ý tưởng (có thể coi là đầu tiên) về PWA, web developers có thể lập trình ứng dụng iOS trên nền safari. Có điều các developers của Apple có vẻ chậm chạp hơn những người đồng nghiệp tại Google, [Safari tụt hậu hơn so với Chrome ](https://m.phillydevshop.com/apples-refusal-to-support-progressive-web-apps-is-a-serious-detriment-to-future-of-the-web-e81b2be29676) và Google với công nghệ PWA đã buộc Apple phải chấp nhận trong 2 bản cập nhật cho macOS và iOS của mình.

### How it works?

![pwa-hiw](https://qmau.me/uploads/_zf1L_UMFEGp7YuJ.jpg)


Một PWA sẽ vẫn là một web apps bình thường bổ sung thêm 2 thành phần là manifest và service worker.
- Manifest:
  File JSON có nhiệm vụ config tất cả thông số của một PWA:
    - short_name
    - icons
    - view mode
    - url của PWA
    - ...
- Service worker: Làm việc như một proxy, khi người dùng sử dụng trang web thì service worker sẽ đóng vai trò đứng ở giữ người dùng và web apps, chịu trách nhiệm cho việc quản lý cache, lấy tài nguyên từ network → nhờ có sw mà web app có thể hoạt động offline được.

### Tại sao?

**User engage facts**
- Websites:
  - **53%** người dùng sẽ từ bỏ việc truy cập một website load quá 3s
  - **1/2** người muốn trang web load dưới **2s**
  - **3/4** ứng dụng web mất hơn **10s** để load
- Native app:
  - Engage tốt hơn nhờ push notification và home screen icons
  - Thời gian load nhanh hơn và sử dụng ngay được mỗi khi khởi động.
- PWA solutions:
  - Làm web app load nhanh hơn
  - Có thể tạo home screen icon
  - Push notifications

**User reach facts**
![user-reach](https://qmau.me/uploads/7lJM86DwyjzofGPF.png)

- Websites: Web browser làm được nhiều thứ hơn một native app, nhanh, gọn hơn.
- Native app: Bạn cần bao nhiêu công đoạn từ lúc biết đến app, cài, cấp permission...?

→ Kết luận
- Ordinary web Apps →　**high** user reach, _low_ user engage
- Native Apps →　_low_ user reach, **high** user engage
- PWA → **high** user reach, **high** user engage

### Tình hình thế giới:

![pwas](https://qmau.me/uploads/oWnCYcQ2cM04mjmF.jpg)


- Chrome, Opera, Firefox đã hỗ trợ đầy đủ PWA, Microsoft Edge vẫn chậm chạp như ông anh IE, sẽ hỗ trợ trong tương lai gần, Samsung internet browser cũng trong danh sách → với các thiết bị android, PWA hoạt động tốt và có đầy đủ các chức năng. Và cuối cùng safari đã hỗ trợ service workers và một vài tính năng chính của PWA trong bản cập nhật mới nhất của Apple. Vậy là gần như tất cả các platform và browser đều đã hỗ trợ service worker.


![pinterest](https://qmau.me/uploads/bmZW6vLuF-wmnBqS.png)


- PWA giúp tăng trải nghiệm người dùng → tạo lợi nhuận cho nhà phát triển ứng dụng. Pinterest tăng **40%** thời gian được sử dụng, doanh thu quảng cáo tăng **40%** và sự gắn kết của người dùng tăng **60%** khi chuyển sang sử dụng PWA viết bằng React, Redux và Webpack. Twitter, instagram, tinder đều cho ra mắt bản lite áp dụng PWA có dung lượng dưới 10mb hoạt động ổn định.

- PWA có thể được cài đặt không thông qua store → tiết kiện được chi phí cho app store, tuy nhiên việc không kiếm được lợi nhuận từ PWA cũng có thể là lý do chính khiến Apple không mấy mặn mà.

![pwa-perform](https://qmau.me/uploads/HZIQXJzyKo4tH8EH.png)

- Perform của website khi sử dụng service worker được cải thiện đáng kể

- [HTTPS trở thành tiêu chuẩn chung cho các websites](https://security.googleblog.com/2016/09/moving-towards-more-secure-web.html) và service worker chỉ làm việc với HTTPS, thêm nữa PWA hỗ trợ đầy đủ các tính năng SEO. **58%** các trang web ecomerce có điểm đánh giá PWA từ 40-60/100 m 41% dưới 40 và chỉ khoảng 1% trên 60 theo kết quả của [Lighthouse](https://developers.google.com/web/tools/lighthouse/) (công cụ đánh giá website của google chrome).

Hãy thử tưởng tượng đến việc các lập trình viên của vnexpress, dân trí hay một số ứng dụng đọc báo khác phải vất vả thế nào để có thể maintain được các ứng dụng của mình trên nhiều platforms khác nhau, trong khi đó, một lập trình viên có kiến thức về responsive design và PWA sử dụng dưới 1 month man có thể tạo ra 1 ứng dụng đa nền tảng hoạt động ổn định có đầy đủ các chức năng của native apps.

Tuy rằng [PWA trên iOS vẫn còn bị giới hạn nhiều](https://medium.com/@firt/pwas-are-coming-to-ios-11-3-cupertino-we-have-a-problem-2ff49fd7d6ea) nhưng trong tương lai không xa, mình nghĩ rằng PWA sẽ được hỗ trợ đầy đủ trên các platforms và browsers.

Để chứng minh cho niềm tin của bản thân, mình sẽ biến blog cá nhân thành một PWA 🤣

## How to make a PWA?
### Manifest
Sử dụng [Manifest generator](https://app-manifest.firebaseapp.com/) để tạo manifest cho trang web

`manifest.json`

```json
{
  "name": "Blog của Mầu",
  "short_name": "qmau.me",
  "theme_color": "#f44336",
  "background_color": "#ffffff",
  "display": "standalone",
  "start_url": "https://qmau.me/",
  "icons": [
    {
      "src": "images/icons/icon-152x152.png",
      "sizes": "152x152",
      "type": "image/png"
    },
  ],
  "splash_pages": null
}
```
Manifest sẽ config các thông số cần thiết với một PWA:
- name → tên của ứng dụng
- short_name → tên hiển thị
- start_url → url của website
- icons → icon của PWA trên homescreen của người dùng

Nếu muốn tìm hiểu cụ thể bạn có thể tham khảo [document của Google](https://developers.google.com/web/fundamentals/web-app-manifest/).
Khai bảo file `manifest.json` bằng thẻ tag meta, tiện thể khai báo thêm một số thẻ tag để safari có thể nhận diện được PWA

`index.html`

```html
<link rel="manifest" href="/manifest.json">
<meta name="theme-color" content="#f44336">
<link rel="icon" href="/images/icons/icon-152x152.png">
<!-- Add to home screen for Safari on iOS-->
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="default">
<meta name="apple-mobile-web-app-title" content="qmau.me">
<link rel="apple-touch-icon" href="/images/icons/icon-152x152.png">
<!-- Add to home screen for Windows-->
<meta name="msapplication-TileImage" content="/images/icons/icon-152x152.png">
<meta name="msapplication-TileColor" content="#000000">
<link rel="manifest" href="/manifest.json">
```

### Service worker
Để có thể sử dụng service worker PWA cần phải đăng ký (register), mình sử dụng [template có sẵn của google](https://github.com/GoogleChromeLabs/sw-precache/blob/master/demo/app/js/service-worker-registration.js).

`sw_reg.js`

```js
'use strict';

if ('serviceWorker' in navigator) {
  window.addEventListener('load', function() {
    navigator.serviceWorker.register('service-worker.js').then(function(reg) {
      reg.onupdatefound = function() {
        var installingWorker = reg.installing;
        installingWorker.onstatechange = function() {
          switch (installingWorker.state) {
            case 'installed':
              if (navigator.serviceWorker.controller) {
                console.log('New or updated content is available.');
              } else {
                console.log('Content is now available offline!');
              }
              break;
            case 'redundant':
              console.error('The installing service worker became redundant.');
              break;
          }
        };
      };
    }).catch(function(e) {
      console.error('Error during service worker registration:', e);
    });
  });
}
```

![pwa-flow](https://qmau.me/uploads/C8GptTj11yw-42Tt.png)


Như đã trình bày ở phần trên, service worker đóng vai trò như một proxy điều hướng cho PWA, tuỳ vào độ phức tạp của app mà sw có thể làm được nhiều thứ. Còn trong trường hợp blog của mình thì nó có nhiệm vụ chính là precache tài nguyên để có thể sử dụng trong điều kiện mạng yếu (hoặc thậm chí là không có mạng).
Một số scenario cache được trình bày cụ thể tại [offline cookbook](https://developers.google.com/web/fundamentals/instant-and-offline/offline-cookbook/) và [serviceworke.rs](https://serviceworke.rs/).

Nếu các bạn muốn cache toàn bộ trang web của mình thì có thể sử dụng module [sw-precache](https://github.com/GoogleChromeLabs/sw-precache) của Google.

Mình thì không thù oán gì với người đọc cũng như cache của các bạn nên mình chọn một cách cache đơn giản như sau:

- Service worker sẽ lấy tài nguyên từ network trước và sau timeout(500ms) nếu chưa load được sẽ lấy ra từ cache.
- Chỉ precache một vài trang cơ bản (home,tags,categories)
- Cache lại các assets file cơ bản để phục vụ cho việc hoạt động offline
- Không cache lại các tài nguyên ảnh để tiết kiệm vài MB cache cho độc giả 🙌

`service_worker.js`
```js
var CACHE = 'cache';
var urlsToCache = [
	'/',
	'/bucket-list',
	'/tag/blog',
  ...
];
var preCacheSrc = [
	'/semantic/dist/semantic.css',
	'/styles/highlight.css',
  ...
];
// precache tài nguyên khi được đăng ký bởi sw_reg.js
self.addEventListener('install', function (evt) {
	console.log('The service worker is being installed.');
	caches.open(CACHE)
		.then(function (cache) {
			console.log('Opened cache');
			return cache.addAll(urlsToCache);
		});
	evt.waitUntil(precache());
});

// khi tài nguyên được gọi
self.addEventListener('fetch', function (evt) {
	console.log('The service worker is serving the asset.');
  // sau 0.6s không load
	evt.respondWith(fromNetwork(evt.request, 500).catch(function () {
    // lấy từ cache
		return fromCache(evt.request);
	}));
    // update cache
	evt.waitUntil(update(evt.request));
});

// lấy tài nguyên từ network
function fromNetwork (request, timeout) {
	return new Promise(function (fulfill, reject) {
		var timeoutId = setTimeout(reject, timeout);
		fetch(request).then(function (response) {
			clearTimeout(timeoutId);
			fulfill(response);
		}, reject);
	});
}

// precache một tí =))
function precache () {
	return caches.open(CACHE).then(function (cache) {
		return cache.addAll(preCacheSrc);
	});
}

// lấy tài nguyên từ cache
function fromCache (request) {
	return caches.open(CACHE).then(function (cache) {
		return cache.match(request).then(function (matching) {
			return matching || Promise.reject('no-match');
		});
	});
}

// update cache
function update (request) {
	return caches.open(CACHE).then(function (cache) {
		return fetch(request).then(function (response) {
			return cache.put(request, response);
		});
	});
}
```

### Deploy, test
![pwa-flow](https://qmau.me/uploads/wDvIA6ENSuPSGPjJ.jpg)

Khá là ổn, cố gắng thêm chút là được all 100 =))

Resource được precache để đảm bảo tốc độ load trang và offline mode

![precache](https://qmau.me/uploads/csUfZG1-KrjzlWm3.jpg)

Test thử trên iOS
- Add to home screen button

![home-add](https://qmau.me/uploads/J8tV5Hw-oDd4NdRQ.jpg)

- Shell app screen

![app-screen](https://qmau.me/uploads/8nl5nNj2_5EjckbD.jpg)

Test thử trên Android (thanks Phúc Long)
- Home screen icon

![home-android](https://qmau.me/uploads/A9wD-jOynfU4u4vF.jpg)

- Shell app screen

![shell-app-android](https://qmau.me/uploads/Vo9n-5c9eTSwJfqO.jpg)


Offline mode

![offline](https://qmau.me/uploads/EiVt0mHoOm4MyMYM.jpg)

_Không load được ảnh do không cache nhưng vẫn load được HTML_

Okay, vậy là mình đã sở hữu một PWA đa nền tảng của riêng mình, có thể viết vào CV là lập trình được iOS và Android rồi (xạo tí 👺)

Một note nhỏ với các bạn: **PWA chỉ sử dụng HTTPS**, các bạn đang sử dụng http thì có thể đọc bài [deployment blog của mình](https://qmau.me/blog/post/blogging-cung-keystone-js-3-deployment), [hướng dẫn ssl của BáchNX](https://mystories.vn/2017/12/09/chuyen-dev-so-2/) hoặc [sử dụng cloudflare của thanh niên Kaito Yuuki](https://tsukie.com/vi/cong-nghe/cai-dat-ssl-cho-website-mien-phi-de-dang-nhanh-chong-voi-cloudflare-chi-vai-buoc-click-chuot/)

## Bàn chút về chuyện tương lai
(_ý kiến cá nhân của người viết_)

Web app vẫn đang hoàn thiện và ưu việt hơn mỗi ngày với nhiều công nghệ mới, trong thời đại của các micro service mỳ ăn liền và sự lên ngôi của javascript thì PWA là một trong những thứ đáng để một web developer quan tâm đến. Dù chưa được hỗ trợ push notification trên iOS nhưng trong 1-2 năm tới, mình nghĩ rằng các ứng dụng như tin tức, thời tiết, đọc sách, các micro-service, thậm chí e-comerce cũng sẽ chuyển dần sang PWA. Còn với các ứng dụng đòi hỏi nhiều tài nguyên từ hệ thống (game,...) thì câu chuyện cũng như các web game với game trên PC vậy, chắc còn phải rất lâu nữa.

Việc có thể đảm bảo được chức năng như native app, sử dụng những công nghệ web mới đòi hỏi ít nhân lực phục vụ nhiều nền tảng khác nhau, dễ maintain, tăng cả reach và engage với người dùng → quá hấp dẫn và đáng để thử.

**Cá nhân mình nghĩ [PWA có một tương lai rất sáng lạn](https://medium.freecodecamp.org/why-progressive-web-apps-are-the-future-of-web-development-13db7dd5f640) phía trước, không chắc chắn nó sẽ thay thế được native app nhưng nó chắc chắn sẽ là "a big thing" với web technology.**

Còn trong tương lai gần, ngay tại thời điểm hiện tại một lập trình viên sử dụng một ngôn ngữ không-liên-quan-một-tẹo-nào đến iOS như nodejs cũng có thể tạo một ứng dụng trên iOS 11.3, và mình-lập trình viên nodejs với kinh nghiệm 20 dòng tự code vừa chứng minh điều đó là hoàn toàn có thể.

### New challenge
Khi sử dụng light house của Chrome mình có để ý đến thông số performance và thử test trên một số trang web khác, đáng ngạc nhiên là hầu hết các trang web đều không đạt được quá 50 điểm. Để phục vụ người dùng có một trải nghiệm tốt hơn mình xin mạnh dạn đề ra KPI load time của qmau.me **<500ms** và sẽ cố gắng note lại những kiến thức mình sẽ tìm hiểu về web optimize, pwa và amp trong thời gian sớm nhất.


## refs
- [Lighthouse](https://developers.google.com/web/tools/lighthouse/)
- [Google-PWA](https://developers.google.com/web/progressive-web-apps/)
- [Google-service worker](https://developers.google.com/web/fundamentals/primers/service-workers/)
- [PWA-kipalog](https://kipalog.com/posts/Progressive-Web-Apps-la-gi)
- [Pinterest PWA](https://medium.com/dev-channel/a-pinterest-progressive-web-app-performance-case-study-3bd6ed2e6154)
- [Twitter lite performance](https://medium.com/@paularmstrong/twitter-lite-and-high-performance-react-progressive-web-apps-at-scale-d28a00e780a3)
- [PWA on iOS](https://medium.com/@firt/progressive-web-apps-on-ios-are-here-d00430dee3a7)
- [PWA libraries](https://medium.com/dev-channel/progressive-web-app-libraries-in-production-b52cad37d34)
- [PWA on all platforms](https://medium.com/@kennethrohde/progressive-web-apps-coming-to-all-chrome-platforms-80e31272e2a8)
- [Next big thing](https://medium.com/progressive-web-apps/who-still-havent-experienced-the-2-years-old-next-big-thing-for-mobile-web-978cc55f821a)

ps: bạn nào biết quán cháo lòng nào ở Tokyo thì giới thiệu với, mai tranh thủ đi ăn để đón gió mùa cho nó đúng vị =))

良い週末を！

また
