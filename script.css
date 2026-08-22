// ===== MENU MOBILE =====
(function() {
    const btnMobile = document.getElementById('mobile-menu-btn');
    const mobileMenu = document.getElementById('mobile-menu');
    const closeBtn = document.getElementById('close-mobile-menu');
    const overlay = document.getElementById('mobile-overlay');

    function openMenu() {
        mobileMenu.classList.add('open');
        mobileMenu.setAttribute('aria-hidden', 'false');
        btnMobile.setAttribute('aria-expanded', 'true');
        overlay.classList.add('active');
        document.body.style.overflow = 'hidden';
    }

    function closeMenu() {
        mobileMenu.classList.remove('open');
        mobileMenu.setAttribute('aria-hidden', 'true');
        btnMobile.setAttribute('aria-expanded', 'false');
        overlay.classList.remove('active');
        document.body.style.overflow = '';
    }

    if (btnMobile) {
        btnMobile.addEventListener('click', openMenu);
    }
    if (closeBtn) {
        closeBtn.addEventListener('click', closeMenu);
    }
    if (overlay) {
        overlay.addEventListener('click', closeMenu);
    }

    document.querySelectorAll('#mobile-menu a').forEach(link => {
        link.addEventListener('click', closeMenu);
    });
})();

// ===== SCROLL: NAVBAR + BACK-TO-TOP =====
(function() {
    const header = document.getElementById('navbar');
    const btnTop = document.getElementById('back-to-top');

    window.addEventListener('scroll', function() {
        if (header) {
            header.classList.toggle('shadow-sm', window.scrollY > 50);
        }
        if (btnTop) {
            if (window.scrollY > 400) {
                btnTop.classList.remove('opacity-0', 'translate-y-4', 'pointer-events-none');
                btnTop.classList.add('opacity-100', 'translate-y-0', 'pointer-events-auto');
            } else {
                btnTop.classList.add('opacity-0', 'translate-y-4', 'pointer-events-none');
                btnTop.classList.remove('opacity-100', 'translate-y-0', 'pointer-events-auto');
            }
        }
    });
})();

// ===== SCROLL REVEAL =====
(function() {
    const revealElements = document.querySelectorAll('.reveal');
    if ('IntersectionObserver' in window) {
        const revealObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                    revealObserver.unobserve(entry.target);
                }
            });
        }, { threshold: 0.12 });
        revealElements.forEach(el => revealObserver.observe(el));
    } else {
        // fallback: mostrar todos
        revealElements.forEach(el => el.classList.add('visible'));
    }
})();

// ===== LGPD MODAL =====
(function() {
    const lgpdModal = document.getElementById('lgpd-modal');
    if (!lgpdModal) return;

    function showLGPD() {
        lgpdModal.classList.add('show');
    }

    function hideLGPD() {
        lgpdModal.classList.remove('show');
    }

    window.acceptAllLGPD = function() {
        const analytics = document.getElementById('cookie-analytics');
        const marketing = document.getElementById('cookie-marketing');
        if (analytics) analytics.checked = true;
        if (marketing) marketing.checked = true;
        localStorage.setItem('lgpd_choice', JSON.stringify({
            essential: true,
            analytics: true,
            marketing: true,
            timestamp: new Date().toISOString()
        }));
        hideLGPD();
    };

    window.saveChoicesLGPD = function() {
        const analytics = document.getElementById('cookie-analytics');
        const marketing = document.getElementById('cookie-marketing');
        const analyticsVal = analytics ? analytics.checked : false;
        const marketingVal = marketing ? marketing.checked : false;
        localStorage.setItem('lgpd_choice', JSON.stringify({
            essential: true,
            analytics: analyticsVal,
            marketing: marketingVal,
            timestamp: new Date().toISOString()
        }));
        hideLGPD();
    };

    window.rejectOptionalLGPD = function() {
        const analytics = document.getElementById('cookie-analytics');
        const marketing = document.getElementById('cookie-marketing');
        if (analytics) analytics.checked = false;
        if (marketing) marketing.checked = false;
        localStorage.setItem('lgpd_choice', JSON.stringify({
            essential: true,
            analytics: false,
            marketing: false,
            timestamp: new Date().toISOString()
        }));
        hideLGPD();
    };

    // Exibir modal se não houver preferência salva
    window.addEventListener('load', function() {
        if (!localStorage.getItem('lgpd_choice')) {
            setTimeout(showLGPD, 1200);
        }
    });

    // Fechar ao clicar no overlay (fora do conteúdo)
    lgpdModal.addEventListener('click', function(e) {
        if (e.target === lgpdModal) {
            hideLGPD();
        }
    });
})();