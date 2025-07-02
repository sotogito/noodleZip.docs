```
<!DOCTYPE html>  
<html lang="en" xmlns:th="http://www.thymeleaf.org">  
<head>  
  <meta charset="utf-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1">  
  <meta name="description" content="Foogra - Discover & Book the best restaurants at the best price">  
  <meta name="author" content="Ansonika">  
  <title>Foogra - Discover & Book the best restaurants at the best price</title>  
  
  <!-- Favicons-->  
  <link rel="shortcut icon" href="img/favicon.ico" type="image/x-icon">  
  <link rel="apple-touch-icon" type="image/x-icon" href="img/apple-touch-icon-57x57-precomposed.png">  
  <link rel="apple-touch-icon" type="image/x-icon" sizes="72x72" href="img/apple-touch-icon-72x72-precomposed.png">  
  <link rel="apple-touch-icon" type="image/x-icon" sizes="114x114" href="img/apple-touch-icon-114x114-precomposed.png">  
  <link rel="apple-touch-icon" type="image/x-icon" sizes="144x144" href="img/apple-touch-icon-144x144-precomposed.png">  
  
  <!-- GOOGLE WEB FONT -->  
  <link rel="preconnect" href="https://fonts.gstatic.com">  
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">  
  <!-- BASE CSS -->  
  <link th:href="@{/css/bootstrap.min.css}" rel="stylesheet">  
  <link th:href="@{/css/style.css}" rel="stylesheet">  
  <!-- SPECIFIC CSS -->  
  <link th:href="@{/css/home.css}" rel="stylesheet">  
  <!-- YOUR CUSTOM CSS -->  
  <link th:href="@{/css/custom.css}" rel="stylesheet">  
  
</head>  
  
<body>  
  
<header class="header clearfix element_to_stick">  
  <div class="container">  
    <div id="logo">  
      <a href="index.html">  
        <img src="img/logo.svg" width="140" height="35" alt="" class="logo_normal">  
        <img src="img/logo_sticky.svg" width="140" height="35" alt="" class="logo_sticky">  
      </a>    </div>    <ul id="top_menu">  
      <li><a href="#sign-in-dialog" id="sign-in" class="login">Sign In</a></li>  
      <li><a href="wishlist.html" class="wishlist_bt_top" title="Your wishlist">Your wishlist</a></li>  
    </ul>    <!-- /top_menu -->  
    <a href="#0" class="open_close">  
      <i class="icon_menu"></i><span>Menu</span>  
    </a>    <nav class="main-menu">  
      <div id="header_menu">  
        <a href="#0" class="open_close">  
          <i class="icon_close"></i><span>Menu</span>  
        </a>        <a href="index.html"><img src="img/logo.svg" width="140" height="35" alt=""></a>  
      </div>      <ul>        <li class="submenu">  
          <a href="#0" class="show-submenu">Home</a>  
          <ul>            <li><a href="index.html">Default</a></li>  
            <li class="third-level"><a href="#0">Sliders - Parallax <strong>New!</strong></a>  
              <ul>                <li><a href="index-16.html">Kenburns slider <strong>New!</strong></a></li>  
                <li><a href="index-8.html">Revolution Slider 1</a></li>  
                <li><a href="index-9.html">Revolution Slider 2</a></li>  
                <li><a href="index-3.html">Owl Carousel</a></li>  
                <li><a href="index-10.html">Parallax Youtube</a></li>  
                <li><a href="index-11.html">Parallax Vimeo</a></li>  
                <li><a href="index-12.html">Parallax Mp4 Video</a></li>  
                <li><a href="index-13.html">Parallax Video Fullscreen</a></li>  
                <li><a href="index-14.html">Parallax Image</a></li>  
              </ul>            </li>            <li><a href="index-15.html">Text Rotator</a></li>  
            <li><a href="index-5.html">Address Autocomplete</a></li>  
            <li><a href="index-6.html">Search Version 2</a></li>  
            <li><a href="index-7.html">Delivery/Takeaway version</a></li>  
            <li><a href="modal-advertise.html">Modal Advertise</a></li>  
            <li><a href="modal-newsletter.html">Modal Newsletter</a></li>  
            <li><a href="index-2.html">Video Bg Fallback Mobile</a></li>  
            <li><a href="index-4.html">GDPR Cookie Bar EU Law</a></li>  
          </ul>        </li>        <li class="submenu">  
          <a href="#0" class="show-submenu">Listing</a>  
          <ul>            <li class="third-level"><a href="#0">List pages</a>  
              <ul>                <li><a href="grid-listing-filterscol.html">List default</a></li>  
                <li><a href="grid-listing-filterscol-map.html">List with map</a></li>  
                <li><a href="listing-map.html">List side map</a></li>  
                <li><a href="grid-listing-filterscol-full-width.html">List full width</a></li>  
                <li><a href="grid-listing-filterscol-full-masonry.html">List Masonry Filter</a></li>  
                <li><a href="grid-listing-filterscol-delivery.html">List Delivery/Takeaway</a></li>  
              </ul>            </li>            <li class="third-level"><a href="#0">Detail pages</a>  
              <ul>                <li><a href="detail-restaurant.html">Detail page 1</a></li>  
                <li><a href="detail-restaurant-2.html">Detail page 2</a></li>  
                <li><a href="detail-restaurant-3.html">Mobile Fixed Booking</a></li>  
                <li><a href="detail-restaurant-delivery.html">Delivery/Takeaway</a></li>  
                <li><a href="detail-restaurant-4.html">Detail Menu Thumbs</a></li>  
                <li><a href="detail-restaurant-5.html">Detail Contact Form</a></li>  
              </ul>            </li>            <li class="third-level"><a href="#0">OpenStreetMap</a>  
              <ul>                <li><a href="grid-listing-filterscol-map-openstreetmap.html">List with map</a></li>  
                <li><a href="listing-map-openstreetmap.html">List side map</a></li>  
                <li><a href="grid-listing-filterscol-full-width-openstreetmap.html">List full width</a></li>  
                <li><a href="grid-listing-filterscol-full-masonry-openstreetmap.html">List Masonry Filter</a></li>  
              </ul>            </li>            <li><a href="submit-restaurant.html">Submit Restaurant</a></li>  
            <li><a href="submit-rider.html">Submit Rider</a></li>  
            <li><a href="wishlist.html">Wishlist</a></li>  
            <li><a href="booking.html">Booking</a></li>  
            <li><a href="confirm.html">Confirm Booking</a></li>  
            <li><a href="confirm-delivery.html">Confirm Order</a></li>  
            <li><a href="booking-delivery-2.html">Order Delivery/Takeaway</a></li>  
            <li><a href="booking-delivery.html">Order Delivery/Takeaway 2</a></li>  
            <li><a href="admin_section/index.html" target="_blank">Admin Section</a></li>  
          </ul>        </li>        <li class="submenu">  
          <a href="#0" class="show-submenu">Other Pages</a>  
          <ul>            <li><a href="404.html">404 Error</a></li>  
            <li><a href="help.html">Help and Faq</a></li>  
            <li><a href="blog.html">Blog</a></li>  
            <li><a href="leave-review.html">Leave a review</a></li>  
            <li><a href="user-logged-1.html">User Logged 1</a></li>  
            <li><a href="user-logged-2.html">User Logged 2</a></li>  
            <li><a href="contacts.html">Contacts</a></li>  
            <li><a href="coming_soon/index.html">Coming Soon</a></li>  
            <li><a href="account.html">Sign Up</a></li>  
            <li><a href="icon-pack-1.html">Icon Pack 1</a></li>  
            <li><a href="icon-pack-2.html">Icon Pack 2</a></li>  
          </ul>        </li>        <li><a href="submit-restaurant.html">Submit</a></li>  
        <li><a href="#0">Buy this template</a></li>  
      </ul>    </nav>  </div></header>  
<!-- /header -->  
<main>  
  
  <h1 th:text="${user.userName}"></h1>  
  <div class="bg_gray">  
    <div class="container margin_60_40">  
      <div class="main_title center">  
        <span><em></em></span>        <h2>좋아요</h2>  
        <p>좋아요 받은 개수 기준으로 주어지는 배지입니다.</p>  
      </div>      <div class="owl-carousel owl-theme categories_carousel">  
        <div class="item">  
          <a href="#6">  
            <span>누적</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>리뷰 좋아요</h3>  
            <small>level 1</small>  
          </a>        </div>        <div class="item">  
          <a href="#6">  
            <span>누적</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>커뮤니티 좋아요</h3>  
            <small>level 4</small>  
          </a>        </div>        <div class="item">  
          <a href="#6">  
            <span>누적</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>커뮤니티 좋아요</h3>  
            <small>level 4</small>  
          </a>        </div>        <div class="item">  
          <a href="#6">  
            <span>누적</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>커뮤니티 좋아요</h3>  
            <small>level 4</small>  
          </a>        </div>        <div class="item">  
          <a href="#6">  
            <span>누적</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>커뮤니티 좋아요</h3>  
            <small>level 4</small>  
          </a>        </div>        <div class="item">  
          <a href="#6">  
            <span>누적</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>커뮤니티 좋아요</h3>  
            <small>level 4</small>  
          </a>        </div>        <div class="item">  
          <a href="#6">  
            <span>누적</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>커뮤니티 좋아요</h3>  
            <small>level 4</small>  
          </a>        </div>        <div class="item">  
          <a href="#6">  
            <span>누적</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>커뮤니티 좋아요</h3>  
            <small>level 4</small>  
          </a>        </div>        <div class="item">  
          <a href="#6">  
            <span>누적</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>커뮤니티 좋아요</h3>  
            <small>level 4</small>  
          </a>        </div>        <div class="item">  
          <a href="#6">  
            <span>누적</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>커뮤니티 좋아요</h3>  
            <small>level 4</small>  
          </a>        </div>      </div>    </div>  </div>  
  <div class="bg_gray">  
    <div class="container margin_60_40">  
      <div class="main_title center">  
        <span><em></em></span>        <h2>소통</h2>  
        <p>커뮤니티 활동을 기준으로 주어지는 배지입니다.</p>  
      </div>      <div class="owl-carousel owl-theme categories_carousel">  
        <div class="item">  
          <a href="#6">  
            <span>누적</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>게시글 작성</h3>  
            <small>면토커</small>  
          </a>        </div>        <div class="item">  
          <a href="#6">  
            <span>누적</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>댓글 작성</h3>  
            <small>댓글장인</small>  
          </a>        </div>      </div>    </div>  </div>  
  <div class="bg_gray">  
    <div class="container margin_60_40">  
      <div class="main_title center">  
        <span><em></em></span>        <h2>지역</h2>  
        <p>라멘을 먹은 지역을 기주능로 주어지는 배지입니다.</p>  
      </div>      <div class="owl-carousel owl-theme categories_carousel">  
        <div class="item">  
          <a href="#6">  
            <span>98</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>서울</h3>  
            <small>골목 탐험가</small>  
          </a>        </div>        <div class="item">  
          <a href="#6">  
            <span>98</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>돈코츠</h3>  
            <small>애호기</small>  
          </a>        </div>      </div>    </div>  </div>  
  <div class="bg_gray">  
    <div class="container margin_60_40">  
      <div class="main_title center">  
        <span><em></em></span>        <h2>라멘 카테고리</h2>  
        <p>라멘 카테고리를 기준으로 주어지는 배지입니다.</p>  
      </div>      <div class="owl-carousel owl-theme categories_carousel">  
        <div class="item">  
          <a href="#6" data-badge-id="1">  
            <span>98</span>  
            <i class="icon-food_icon_pizza"></i>  
            <h3>돈코츠</h3>  
            <small>애호기</small>  
          </a>        </div>      </div>    </div>  </div>  <div class="bg_gray">  
    <div class="container margin_60_40">  
      <div class="main_title center">  
        <span><em></em></span>        <h2>이벤트</h2>  
        <p>이벤트성 배지입니다.</p>  
      </div>      <h2>배지가 없습니다.</h2>  
    </div>  </div>  
</main>  
  
  
<footer>  
  <div class="container">  
    <div class="row">  
      <div class="col-lg-3 col-md-6">  
        <h3 data-bs-target="#collapse_1">Quick Links</h3>  
        <div class="collapse dont-collapse-sm links" id="collapse_1">  
          <ul>            <li><a href="submit-rider.html">Become a Rider</a></li>  
            <li><a href="submit-restaurant.html">Add your restaurant</a></li>  
            <li><a href="help.html">Help</a></li>  
            <li><a href="account.html">My account</a></li>  
            <li><a href="blog.html">Blog</a></li>  
            <li><a href="contacts.html">Contacts</a></li>  
          </ul>        </div>      </div>      <div class="col-lg-3 col-md-6">  
        <h3 data-bs-target="#collapse_2">Categories</h3>  
        <div class="collapse dont-collapse-sm links" id="collapse_2">  
          <ul>            <li><a href="grid-listing-filterscol.html">Top Categories</a></li>  
            <li><a href="grid-listing-filterscol-full-masonry.html">Best Rated</a></li>  
            <li><a href="grid-listing-filterscol-full-width.html">Best Price</a></li>  
            <li><a href="grid-listing-filterscol-full-masonry.html">Latest Submissions</a></li>  
          </ul>        </div>      </div>      <div class="col-lg-3 col-md-6">  
        <h3 data-bs-target="#collapse_3">Contacts</h3>  
        <div class="collapse dont-collapse-sm contacts" id="collapse_3">  
          <ul>            <li><i class="icon_house_alt"></i>97845 Baker st. 567<br>Los Angeles - US</li>  
            <li><i class="icon_mobile"></i>+94 423-23-221</li>  
            <li><i class="icon_mail_alt"></i><a href="#0">info@domain.com</a></li>  
          </ul>        </div>      </div>      <div class="col-lg-3 col-md-6">  
        <h3 data-bs-target="#collapse_4">Keep in touch</h3>  
        <div class="collapse dont-collapse-sm" id="collapse_4">  
          <div id="newsletter">  
            <div id="message-newsletter"></div>  
            <form method="post" action="assets/newsletter.php" name="newsletter_form" id="newsletter_form">  
              <div class="form-group">  
                <input type="email" name="email_newsletter" id="email_newsletter" class="form-control" placeholder="Your email">  
                <button type="submit" id="submit-newsletter"><i class="arrow_carrot-right"></i></button>  
              </div>            </form>          </div>          <div class="follow_us">  
            <h5>Follow Us</h5>  
            <ul>              <li><a href="#0"><i class="bi bi-facebook"></i></a></li>  
              <li><a href="#0"><i class="bi bi-twitter-x"></i></a></li>  
              <li><a href="#0"><i class="bi bi-instagram"></i></a></li>  
              <li><a href="#0"><i class="bi bi-tiktok"></i></a></li>  
              <li><a href="#0"><i class="bi bi-whatsapp"></i></a></li>  
            </ul>          </div>        </div>      </div>    </div>    <!-- /row-->  
    <hr>  
    <div class="row add_bottom_25">  
      <div class="col-lg-6">  
        <ul class="footer-selector clearfix">  
          <li>            <div class="styled-select lang-selector">  
              <select>                <option value="English" selected>English</option>  
                <option value="French">French</option>  
                <option value="Spanish">Spanish</option>  
                <option value="Russian">Russian</option>  
              </select>            </div>          </li>          <li>            <div class="styled-select currency-selector">  
              <select>                <option value="US Dollars" selected>US Dollars</option>  
                <option value="Euro">Euro</option>  
              </select>            </div>          </li>          <li><img src="data:image/gif;base64,R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==" data-src="img/cards_all.svg" alt="" width="198" height="30" class="lazy"></li>  
        </ul>      </div>      <div class="col-lg-6">  
        <ul class="additional_links">  
          <li><a href="#0">Terms and conditions</a></li>  
          <li><a href="#0">Privacy</a></li>  
          <li><span>© Foogra</span></li>  
        </ul>      </div>    </div>  </div></footer>  
<!--/footer-->  
  
<div id="toTop"></div><!-- Back to top button -->  
<div class="layer"></div><!-- Opacity Mask Menu Mobile -->  
  
<!--- 배지 상세 모달 -->  
<div class="modal-overlay" id="badgeModal">  
  <div class="modal-container">  
    <button class="modal-close" id="modalClose">&times;</button>  
    <!-- 로딩 상태 -->  
    <div class="modal-loading" id="modalLoading">  
      <div class="loading-spinner"></div>  
    </div>    <!-- 모달 내용 -->  
    <div class="modal-content" id="modalContent" style="display: none;">  
      <!-- 모달 헤더 -->  
      <div class="modal-header">  
        <!-- 상단 버튼들 - 왼쪽 위로 이동 -->  
        <div class="modal-top-buttons">  
          <button class="top-button" id="hideBadgeBtn">  
            배지 숨기기  
          </button>  
          <button class="top-button" id="favoriteBadgeBtn">  
            즐겨찾기  
          </button>  
        </div>        <img src="https://via.placeholder.com/120x120?text=Badge" alt="배지이미지"  
             class="badge-main-image" id="badgeMainImage">  
        <h2 class="badge-name" id="badgeName">배지 이름</h2>  
        <p class="badge-description" id="badgeDescription">  
          배지 설명이 여기에 표시됩니다.  
        </p>  
      </div>      <!-- 모달 바디 -->  
      <div class="modal-body">  
        <h3 class="level-section-title">레벨별 배지</h3>  
        <div class="badge-levels-grid" id="badgeLevelsGrid">  
          <!-- 레벨별 배지가 여기에 동적으로 추가됩니다 -->  
        </div>  
      </div>    </div>  </div></div>  
  
<!-- COMMON SCRIPTS -->  
<script src="js/common_scripts.min.js"></script>  
<script src="assets/validate.js"></script>  
<script>  
  $(".categories_carousel .item a").hover(  
    function(){$(this).find("i").toggleClass("rotate-x");}  
  );  
</script>  
  
<script>  
  const modal = document.getElementById('badgeModal');  
  const modalClose = document.getElementById('modalClose');  
  const modalLoading = document.getElementById('modalLoading');  
  const modalContent = document.getElementById('modalContent');  
  
  // 배지 상세 정보 (실제로는 API에서 가져올 데이터)  
  const badgeData = {  
    1: {  
      name: "리뷰 좋아요",  
      description: "리뷰에 받은 좋아요 수를 기준으로 주어지는 배지입니다. 다른 사용자들에게 도움이 되는 리뷰를 작성해보세요!",  
      mainImage: "https://via.placeholder.com/120x120?text=리뷰",  
      levels: [  
        { name: "첫 좋아요", condition: "좋아요 1개", image: "https://via.placeholder.com/60x60?text=Lv1" },  
        { name: "인기 리뷰어", condition: "좋아요 10개", image: "https://via.placeholder.com/60x60?text=Lv2" },  
        { name: "리뷰 마스터", condition: "좋아요 50개", image: "https://via.placeholder.com/60x60?text=Lv3" },  
        { name: "리뷰 전설", condition: "좋아요 100개", image: "https://via.placeholder.com/60x60?text=Lv4" },  
        { name: "리뷰 신", condition: "좋아요 500개", image: "https://via.placeholder.com/60x60?text=Lv5" },  
        { name: "궁극의 리뷰어", condition: "좋아요 1000개", image: "https://via.placeholder.com/60x60?text=Lv6" }  
      ]  
    },  
    2: {  
      name: "커뮤니티 좋아요",  
      description: "커뮤니티 게시글에 받은 좋아요 수를 기준으로 주어지는 배지입니다. 활발한 소통으로 배지를 획득해보세요!",  
      mainImage: "https://via.placeholder.com/120x120?text=커뮤니티",  
      levels: [  
        { name: "소통 시작", condition: "좋아요 1개", image: "https://via.placeholder.com/60x60?text=Lv1" },  
        { name: "인기글 작성자", condition: "좋아요 20개", image: "https://via.placeholder.com/60x60?text=Lv2" },  
        { name: "커뮤니티 스타", condition: "좋아요 100개", image: "https://via.placeholder.com/60x60?text=Lv3" },  
        { name: "화제의 인물", condition: "좋아요 300개", image: "https://via.placeholder.com/60x60?text=Lv4" },  
        { name: "커뮤니티 리더", condition: "좋아요 1000개", image: "https://via.placeholder.com/60x60?text=Lv5" }  
      ]  
    }  
  };  
  // 모달 열기  
  function openBadgeModal(badgeId) {  
    modal.classList.add('show');  
    document.body.style.overflow = 'hidden'; // 스크롤 방지  
  
    // 로딩 표시    modalLoading.style.display = 'flex';  
    modalContent.style.display = 'none';  
  
    // 실제로는 여기서 API 호출  
    setTimeout(() => {  
      loadBadgeData(badgeId);  
    }, 500);  
  }  
  // 배지 데이터 로드 및 모달 내용 업데이트  
  function loadBadgeData(badgeId) {  
    const data = badgeData[badgeId];  
  
    if (!data) {  
      console.error('배지 데이터를 찾을 수 없습니다:', badgeId);  
      return;  
    }  
    // 메인 정보 업데이트  
    document.getElementById('badgeMainImage').src = data.mainImage;  
    document.getElementById('badgeMainImage').alt = data.name;  
    document.getElementById('badgeName').textContent = data.name;  
    document.getElementById('badgeDescription').textContent = data.description;  
    // 레벨별 배지 그리드 생성  
    const levelsGrid = document.getElementById('badgeLevelsGrid');  
    levelsGrid.innerHTML = '';  
    data.levels.forEach(level => {  
      const levelItem = document.createElement('div');  
      levelItem.className = 'badge-level-item';  
  
      levelItem.innerHTML = `  
                <img src="${level.image}" alt="${level.name}" class="level-badge-image">  
                <div class="level-name">${level.name}</div>  
                <div class="level-condition">${level.condition}</div>  
            `;  
  
      levelsGrid.appendChild(levelItem);  
    });  
    // 로딩 숨기고 내용 표시  
    modalLoading.style.display = 'none';  
    modalContent.style.display = 'block';  
  }  
  // 모달 닫기  
  function closeBadgeModal() {  
    modal.classList.remove('show');  
    document.body.style.overflow = ''; // 스크롤 복원  
  }  
  // 이벤트 리스너  
  modalClose.addEventListener('click', closeBadgeModal);  
  // 모달 오버레이 클릭 시 닫기  
  modal.addEventListener('click', (e) => {  
    if (e.target === modal) {  
      closeBadgeModal();  
    }  
  });  
  // ESC 키로 모달 닫기  
  document.addEventListener('keydown', (e) => {  
    if (e.key === 'Escape' && modal.classList.contains('show')) {  
      closeBadgeModal();  
    }  
  });  
  // 상단 버튼 이벤트  
  const hideBadgeBtn = document.getElementById('hideBadgeBtn');  
  const favoriteBadgeBtn = document.getElementById('favoriteBadgeBtn');  
  
  hideBadgeBtn.addEventListener('click', () => {  
    hideBadgeBtn.classList.toggle('active');  
    // 실제로는 여기서 배지 숨기기 API 호출  
    console.log('배지 숨기기 토글');  
  });  
  
  favoriteBadgeBtn.addEventListener('click', () => {  
    favoriteBadgeBtn.classList.toggle('active');  
    // 실제로는 여기서 즐겨찾기 API 호출  
    console.log('즐겨찾기 토글');  
  });  
  // 배지 아이템 클릭 이벤트 (실제 사용 시 이 부분을 적용)  
  document.addEventListener('DOMContentLoaded', () => {  
    // 모든 배지 아이템에 클릭 이벤트 추가  
    document.querySelectorAll('.categories_carousel .item a').forEach(item => {  
      item.addEventListener('click', (e) => {  
        e.preventDefault();  
        const badgeId = item.getAttribute('data-badge-id');  
        if (badgeId) {  
          openBadgeModal(badgeId);  
        }  
      });  
    });  
  });  
  // API 호출 함수 (실제 구현 시 사용)  
  async function fetchBadgeData(badgeId) {  
    try {  
      const response = await fetch(`/api/badges/${badgeId}`);  
      const data = await response.json();  
      return data;  
    } catch (error) {  
      console.error('배지 데이터 로드 실패:', error);  
      return null;  
    }  
  }  
</script>  
</body>  
</html>
```

NORMAL