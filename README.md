<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Napoli Pizzaria Restaurante | Tagus</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;500;600;700&family=Montserrat:wght@300;400;500;600;700&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html, body {
            width: 100%;
            overflow-x: hidden;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            color: #2D2D2D;
            line-height: 1.7;
            background: #FFFFFF;
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: 'Cormorant Garamond', serif;
            font-weight: 600;
            line-height: 1.2;
        }

        /* NAVBAR */
        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            z-index: 9999;
            padding: 24px 60px;
            border-bottom: 1px solid rgba(232, 232, 232, 0.5);
            transition: padding 0.3s ease, box-shadow 0.3s ease;
        }

        .navbar.scrolled {
            padding: 16px 60px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.08);
        }

        .nav-inner {
            max-width: 1440px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'Cormorant Garamond', serif;
            font-size: 32px;
            font-weight: 700;
            color: #D4332A;
            text-decoration: none;
            transition: transform 0.2s ease;
        }

        .logo:hover {
            transform: scale(1.03);
        }

        .nav-links {
            display: flex;
            gap: 48px;
            list-style: none;
            align-items: center;
        }

        .nav-links li a:not(.nav-cta) {
            text-decoration: none;
            color: #2D2D2D;
            font-weight: 500;
            font-size: 14px;
            letter-spacing: 0.5px;
            text-transform: uppercase;
            position: relative;
            transition: color 0.2s ease;
        }

        .nav-links li a:not(.nav-cta)::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 0;
            height: 2px;
            background: #D4332A;
            transition: width 0.3s ease;
        }

        .nav-links li a:not(.nav-cta):hover {
            color: #D4332A;
        }

        .nav-links li a:not(.nav-cta):hover::after {
            width: 100%;
        }

        /* ✅ BOTÃO CTA CORRIGIDO - SEM BUGS */
        .nav-cta {
            background: #D4332A;
            color: #FFFFFF !important;
            padding: 14px 32px;
            border-radius: 2px;
            text-decoration: none !important;
            font-weight: 600;
            font-size: 13px;
            letter-spacing: 1px;
            text-transform: uppercase;
            transition: all 0.3s ease;
            display: inline-block;
        }

        .nav-cta:hover {
            background: #B02923;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(212, 51, 42, 0.4);
            color: #FFFFFF !important;
        }

        /* HERO */
        .hero {
            width: 100%;
            height: 100vh;
            min-height: 700px;
            background: linear-gradient(135deg, rgba(28, 28, 28, 0.5) 0%, rgba(28, 28, 28, 0.3) 100%),
                        url('https://images.unsplash.com/photo-1513104890138-7c749659a591?w=1920&q=90') center center/cover no-repeat;
            background-attachment: fixed;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: #FFFFFF;
            margin-top: 80px;
            position: relative;
        }

        .hero-inner {
            max-width: 1000px;
            padding: 0 60px;
            position: relative;
            z-index: 2;
            animation: fadeInUp 1s ease;
        }

        .hero h1 {
            font-size: 96px;
            font-weight: 700;
            margin-bottom: 32px;
            letter-spacing: -3px;
        }

        .hero p {
            font-size: 20px;
            margin-bottom: 48px;
            font-weight: 300;
            line-height: 1.8;
        }

        .hero-buttons {
            display: flex;
            gap: 24px;
            justify-content: center;
            flex-wrap: wrap;
        }

        /* BOTÕES */
        .btn {
            padding: 18px 48px;
            border-radius: 2px;
            text-decoration: none;
            font-weight: 600;
            font-size: 13px;
            letter-spacing: 1.5px;
            text-transform: uppercase;
            display: inline-block;
            transition: all 0.2s ease;
        }

        .btn-primary {
            background: #D4332A;
            color: #FFFFFF;
            border: 2px solid #D4332A;
        }

        .btn-primary:hover {
            background: #B02923;
            transform: translateY(-2px);
        }

        .btn-secondary {
            background: transparent;
            color: #FFFFFF;
            border: 2px solid #FFFFFF;
        }

        .btn-secondary:hover {
            background: #FFFFFF;
            color: #D4332A;
            transform: translateY(-2px);
        }

        /* FLOATING BADGE */
        .floating-badge {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: #FFFFFF;
            color: #2D2D2D;
            width: 80px;
            height: 80px;
            border-radius: 50%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            font-size: 12px;
            font-weight: 700;
            box-shadow: 0 8px 30px rgba(0,0,0,0.15);
            z-index: 9998;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .floating-badge:hover {
            transform: scale(1.05);
        }

        .floating-badge .rating {
            font-size: 28px;
            line-height: 1;
            margin-bottom: 4px;
            color: #D4332A;
            font-weight: 700;
        }

        .floating-badge .source {
            font-size: 11px;
            color: #6B6B6B;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* SCROLL REVEAL */
        .scroll-reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.6s ease;
        }

        .scroll-reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* ABOUT */
        .about {
            width: 100%;
            padding: 140px 60px;
            background: #FFFFFF;
        }

        .about-inner {
            max-width: 1440px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 100px;
            align-items: center;
        }

        .about-image-wrapper {
            position: relative;
            overflow: hidden;
            border-radius: 2px;
        }

        .about-image {
            width: 100%;
            height: 700px;
            object-fit: cover;
            transition: transform 0.6s ease;
        }

        .about-image-wrapper:hover .about-image {
            transform: scale(1.05);
        }

        .about-image-overlay {
            position: absolute;
            top: 20px;
            right: 20px;
            background: #D4332A;
            color: white;
            padding: 20px 30px;
            border-radius: 2px;
            font-family: 'Cormorant Garamond', serif;
            font-size: 24px;
            font-weight: 700;
            box-shadow: 0 8px 30px rgba(0,0,0,0.2);
        }

        .about-content h2 {
            font-size: 64px;
            margin-bottom: 28px;
            color: #1C1C1C;
        }

        .about-content p {
            font-size: 17px;
            line-height: 2;
            color: #6B6B6B;
            margin-bottom: 24px;
            font-weight: 300;
        }

        .about-features {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 32px;
            margin-top: 56px;
        }

        .feature {
            padding: 24px;
            background: #FAF8F5;
            border-radius: 8px;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .feature:hover {
            transform: translateY(-4px);
            border-color: #D4332A;
            box-shadow: 0 8px 20px rgba(0,0,0,0.08);
        }

        .feature-icon {
            width: 40px;
            height: 40px;
            margin-bottom: 16px;
        }

        .feature-icon svg {
            width: 100%;
            height: 100%;
            fill: #D4332A;
        }

        .feature h4 {
            font-size: 18px;
            color: #1C1C1C;
            margin-bottom: 8px;
        }

        .feature p {
            font-size: 14px;
            color: #6B6B6B;
            margin: 0;
        }

        /* TEAM SECTION */
        .team {
            width: 100%;
            padding: 140px 60px;
            background: #FFFFFF;
        }

        .team-inner {
            max-width: 1440px;
            margin: 0 auto;
        }

        .team-header {
            text-align: center;
            max-width: 900px;
            margin: 0 auto 80px;
        }

        .team-header h2 {
            font-size: 64px;
            color: #1C1C1C;
            margin-bottom: 28px;
        }

        .team-header p {
            font-size: 18px;
            color: #6B6B6B;
            line-height: 1.9;
        }

        .team-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 48px;
        }

        .team-card {
            text-align: center;
            transition: all 0.3s ease;
        }

        .team-card:hover {
            transform: translateY(-8px);
        }

        .team-photo {
            width: 100%;
            height: 320px;
            border-radius: 2px;
            overflow: hidden;
            margin-bottom: 24px;
            position: relative;
        }

        .team-photo img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .team-card:hover .team-photo img {
            transform: scale(1.1);
        }

        .team-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(to top, rgba(212,51,42,0.9), transparent);
            padding: 24px;
            transform: translateY(100%);
            transition: transform 0.3s ease;
        }

        .team-card:hover .team-overlay {
            transform: translateY(0);
        }

        .team-social {
            display: flex;
            gap: 12px;
            justify-content: center;
        }

        .team-social a {
            width: 32px;
            height: 32px;
            background: #FFFFFF;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #D4332A;
            transition: all 0.2s ease;
        }

        .team-social a:hover {
            background: #D4332A;
            color: #FFFFFF;
            transform: scale(1.1);
        }

        .team-card h3 {
            font-size: 24px;
            color: #1C1C1C;
            margin-bottom: 8px;
        }

        .team-card .role {
            font-size: 14px;
            color: #D4332A;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 12px;
        }

        .team-card p {
            font-size: 14px;
            color: #6B6B6B;
            line-height: 1.6;
        }

        /* STATS */
        .stats {
            width: 100%;
            padding: 100px 60px;
            background: linear-gradient(135deg, #D4332A 0%, #B22222 100%);
            color: white;
        }

        .stats-inner {
            max-width: 1440px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 60px;
        }

        .stat-item {
            text-align: center;
            opacity: 0;
            transform: scale(0.9);
            transition: all 0.5s ease;
        }

        .stat-item.active {
            opacity: 1;
            transform: scale(1);
        }

        .stat-number {
            font-size: 72px;
            font-weight: 700;
            font-family: 'Cormorant Garamond', serif;
            margin-bottom: 16px;
            line-height: 1;
        }

        .stat-label {
            font-size: 16px;
            text-transform: uppercase;
            letter-spacing: 2px;
            font-weight: 600;
        }

        /* MENU */
        .menu {
            width: 100%;
            padding: 140px 60px;
            background: #FAF8F5;
        }

        .menu-inner {
            max-width: 1440px;
            margin: 0 auto;
        }

        .menu-header {
            text-align: center;
            max-width: 900px;
            margin: 0 auto 60px;
        }

        .menu-header h2 {
            font-size: 64px;
            color: #1C1C1C;
            margin-bottom: 28px;
        }

        .menu-header p {
            font-size: 18px;
            color: #6B6B6B;
            line-height: 1.9;
        }

        .menu-tabs {
            display: flex;
            justify-content: center;
            gap: 24px;
            margin-bottom: 60px;
            flex-wrap: wrap;
        }

        .menu-tab {
            padding: 14px 32px;
            background: #FFFFFF;
            border: 2px solid #E8E8E8;
            border-radius: 2px;
            font-size: 14px;
            font-weight: 600;
            letter-spacing: 1px;
            text-transform: uppercase;
            cursor: pointer;
            transition: all 0.2s ease;
            color: #2D2D2D;
        }

        .menu-tab.active {
            background: #D4332A;
            color: #FFFFFF;
            border-color: #D4332A;
        }

        .menu-tab:hover:not(.active) {
            border-color: #D4332A;
        }

        .menu-content {
            display: none;
        }

        .menu-content.active {
            display: block;
            animation: fadeIn 0.4s ease;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 48px;
        }

        .menu-card {
            background: #FFFFFF;
            border-radius: 2px;
            overflow: hidden;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            cursor: pointer;
        }

        .menu-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 30px rgba(0,0,0,0.12);
        }

        .menu-card-image-wrapper {
            position: relative;
            overflow: hidden;
            height: 320px;
        }

        .menu-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .menu-card:hover img {
            transform: scale(1.1);
        }

        .menu-card-badge {
            position: absolute;
            top: 16px;
            right: 16px;
            background: #D4332A;
            color: white;
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .menu-card-content {
            padding: 36px;
        }

        .menu-card h3 {
            font-size: 28px;
            color: #1C1C1C;
            margin-bottom: 16px;
            transition: color 0.2s ease;
        }

        .menu-card:hover h3 {
            color: #D4332A;
        }

        .menu-card .price {
            font-size: 32px;
            color: #D4332A;
            font-weight: 700;
            margin-bottom: 16px;
            display: block;
        }

        .menu-card p {
            color: #6B6B6B;
            font-size: 15px;
            line-height: 1.8;
        }

        /* EXPERIENCE */
        .experience {
            width: 100%;
            padding: 140px 60px;
            background: #1C1C1C;
            color: #FFFFFF;
        }

        .experience-inner {
            max-width: 1440px;
            margin: 0 auto;
        }

        .experience-header {
            text-align: center;
            max-width: 900px;
            margin: 0 auto 80px;
        }

        .experience-header h2 {
            font-size: 64px;
            color: #FFFFFF;
            margin-bottom: 28px;
        }

        .experience-header p {
            font-size: 18px;
            color: rgba(255, 255, 255, 0.75);
            line-height: 1.9;
        }

        .experience-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 56px;
        }

        .experience-card {
            text-align: center;
            padding: 40px;
            background: rgba(255,255,255,0.05);
            border-radius: 8px;
            border: 1px solid rgba(255,255,255,0.1);
            transition: all 0.3s ease;
        }

        .experience-card:hover {
            transform: translateY(-8px);
            background: rgba(255,255,255,0.1);
            border-color: #D4332A;
        }

        .experience-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, #D4332A, #B22222);
            border-radius: 50%;
            margin: 0 auto 28px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: transform 0.3s ease;
        }

        .experience-card:hover .experience-icon {
            transform: rotate(360deg);
        }

        .experience-icon svg {
            width: 40px;
            height: 40px;
            fill: #FFFFFF;
        }

        .experience-card h3 {
            font-size: 22px;
            margin-bottom: 16px;
            color: #FFFFFF;
        }

        .experience-card p {
            color: rgba(255, 255, 255, 0.7);
            line-height: 1.8;
            font-size: 15px;
        }

        /* GALLERY */
        .gallery {
            width: 100%;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 0;
        }

        .gallery-item {
            width: 100%;
            height: 400px;
            overflow: hidden;
            position: relative;
            cursor: pointer;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.15);
        }

        .gallery-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(212,51,42,0.85), rgba(28,28,28,0.85));
            opacity: 0;
            transition: opacity 0.4s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 24px;
            font-weight: 700;
        }

        .gallery-item:hover .gallery-overlay {
            opacity: 1;
        }

        /* TESTIMONIALS - CORRIGIDO */
        .testimonials {
            width: 100%;
            padding: 140px 60px 180px;
            background: #FAF8F5;
        }

        .testimonials-inner {
            max-width: 1440px;
            margin: 0 auto;
        }

        .testimonials-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .testimonials-header h2 {
            font-size: 64px;
            color: #1C1C1C;
            margin-bottom: 20px;
        }

        .google-rating {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 16px;
            margin-bottom: 12px;
        }

        .google-logo {
            font-size: 20px;
            font-weight: 700;
            color: #4285F4;
        }

        .overall-rating {
            font-size: 48px;
            font-weight: 700;
            color: #1C1C1C;
        }

        .stars-large {
            display: flex;
            gap: 4px;
            color: #FBBC04;
            font-size: 32px;
        }

        .review-count {
            color: #6B6B6B;
            font-size: 16px;
        }

        .reviews-carousel-container {
            position: relative;
            overflow: visible;
            margin-top: 40px;
            padding: 20px 0;
        }

        .reviews-carousel {
            display: flex;
            gap: 32px;
            transition: transform 0.4s ease;
        }

        .review-card {
            min-width: calc(33.333% - 22px);
            background: #FFFFFF;
            padding: 32px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
            border: 1px solid #E8E8E8;
            flex-shrink: 0;
            transition: all 0.3s ease;
            position: relative;
        }

        .review-card:hover {
            transform: translateY(-12px);
            box-shadow: 0 16px 40px rgba(0,0,0,0.15);
            border-color: #D4332A;
            z-index: 10;
        }

        .review-header {
            display: flex;
            align-items: center;
            gap: 16px;
            margin-bottom: 20px;
        }

        .reviewer-avatar {
            width: 48px;
            height: 48px;
            border-radius: 50%;
            background: linear-gradient(135deg, #D4332A, #B22222);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: 700;
            font-size: 18px;
            flex-shrink: 0;
        }

        .reviewer-info h4 {
            font-size: 16px;
            color: #1C1C1C;
            margin-bottom: 4px;
            font-family: 'Montserrat', sans-serif;
            font-weight: 600;
        }

        .review-stars {
            display: flex;
            gap: 2px;
            color: #FBBC04;
            font-size: 16px;
        }

        .review-date {
            color: #6B6B6B;
            font-size: 13px;
            margin-top: 4px;
        }

        .review-text {
            color: #2D2D2D;
            font-size: 15px;
            line-height: 1.7;
            margin-bottom: 16px;
        }

        .google-badge {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            color: #6B6B6B;
            font-size: 12px;
        }

        .google-badge svg {
            width: 14px;
            height: 14px;
            fill: currentColor;
        }

        .carousel-controls {
            display: flex;
            justify-content: center;
            gap: 16px;
            margin-top: 40px;
        }

        .carousel-btn {
            width: 48px;
            height: 48px;
            border-radius: 50%;
            background: #FFFFFF;
            border: 2px solid #E8E8E8;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.2s ease;
            font-size: 20px;
            color: #2D2D2D;
        }

        .carousel-btn:hover:not(:disabled) {
            border-color: #D4332A;
            color: #D4332A;
            transform: scale(1.05);
        }

        .carousel-btn:disabled {
            opacity: 0.3;
            cursor: not-allowed;
        }

        /* LOCATION */
        .location {
            width: 100%;
            padding: 140px 60px;
            background: #FFFFFF;
        }

        .location-inner {
            max-width: 1440px;
            margin: 0 auto;
        }

        .location-header {
            text-align: center;
            max-width: 900px;
            margin: 0 auto 80px;
        }

        .location-header h2 {
            font-size: 64px;
            color: #1C1C1C;
            margin-bottom: 28px;
        }

        .location-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 80px;
        }

        .location-info h3 {
            font-size: 24px;
            color: #1C1C1C;
            margin-bottom: 12px;
        }

        .location-info p {
            font-size: 16px;
            color: #6B6B6B;
            line-height: 1.9;
            margin-bottom: 48px;
        }

        .location-map {
            width: 100%;
            height: 600px;
            background: #E5E5E5;
            border-radius: 2px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #6B6B6B;
            transition: all 0.3s ease;
        }

        .location-map:hover {
            box-shadow: 0 12px 30px rgba(0,0,0,0.1);
        }

        /* CTA */
        .cta {
            width: 100%;
            padding: 160px 60px;
            background: linear-gradient(135deg, #D4332A 0%, #B22222 100%);
            text-align: center;
            color: #FFFFFF;
        }

        .cta h2 {
            font-size: 64px;
            margin-bottom: 28px;
            color: #FFFFFF;
        }

        .cta p {
            font-size: 20px;
            margin-bottom: 48px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-buttons {
            display: flex;
            gap: 24px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn-white {
            background: #FFFFFF;
            color: #D4332A;
            border: 2px solid #FFFFFF;
        }

        .btn-white:hover {
            background: transparent;
            color: #FFFFFF;
            transform: translateY(-2px);
        }

        /* FOOTER */
        footer {
            width: 100%;
            padding: 100px 60px 48px;
            background: #1C1C1C;
            color: rgba(255, 255, 255, 0.75);
        }

        .footer-inner {
            max-width: 1440px;
            margin: 0 auto;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr 1fr;
            gap: 80px;
            margin-bottom: 80px;
        }

        .footer-section h3 {
            color: #FFFFFF;
            font-size: 24px;
            margin-bottom: 28px;
        }

        .footer-section p {
            line-height: 1.9;
            margin-bottom: 24px;
            font-size: 15px;
        }

        .footer-bottom {
            padding-top: 48px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            text-align: center;
            color: rgba(255, 255, 255, 0.5);
            font-size: 14px;
        }

        /* ANIMATIONS */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* RESPONSIVE */
        @media (max-width: 968px) {
            .nav-links { display: none; }
            .hero h1 { font-size: 56px; }
            .about-inner { grid-template-columns: 1fr; }
            .menu-grid { grid-template-columns: repeat(2, 1fr); }
            .stats-inner { grid-template-columns: repeat(2, 1fr); }
            .team-grid { grid-template-columns: repeat(2, 1fr); }
            .experience-grid { grid-template-columns: repeat(2, 1fr); }
            .gallery-grid { grid-template-columns: repeat(2, 1fr); }
            .review-card { min-width: calc(50% - 16px); }
            .location-grid { grid-template-columns: 1fr; }
            .footer-grid { grid-template-columns: 1fr; }
        }

        @media (max-width: 640px) {
            .navbar { padding: 24px; }
            .hero, .about, .team, .menu, .experience, .testimonials, .location, .cta, footer {
                padding: 80px 24px;
            }
            .hero h1 { font-size: 42px; }
            .about-content h2,
            .team-header h2,
            .menu-header h2,
            .experience-header h2,
            .testimonials-header h2,
            .location-header h2,
            .cta h2 { font-size: 36px; }
            .menu-grid { grid-template-columns: 1fr; }
            .stats-inner { grid-template-columns: 1fr; }
            .team-grid { grid-template-columns: 1fr; }
            .experience-grid { grid-template-columns: 1fr; }
            .gallery-grid { grid-template-columns: 1fr; }
            .review-card { min-width: 100%; }
        }
    </style>
</head>
<body>

    <!-- FLOATING BADGE -->
    <div class="floating-badge" onclick="window.location.href='#testimonials'">
        <div class="rating">4.8</div>
        <div class="source">Google</div>
    </div>

    <!-- NAVBAR -->
    <nav class="navbar" id="navbar">
        <div class="nav-inner">
            <a href="#" class="logo">Napoli</a>
            <ul class="nav-links">
                <li><a href="#about">Sobre</a></li>
                <li><a href="#team">Equipa</a></li>
                <li><a href="#menu">Menu</a></li>
                <li><a href="#location">Localização</a></li>
                <li><a href="#contact" class="nav-cta">Reservar</a></li>
            </ul>
        </div>
    </nav>

    <!-- HERO -->
    <section class="hero">
        <div class="hero-inner">
            <h1>Napoli Pizzaria</h1>
            <p>Autêntica tradição italiana no coração de Tagus. Pizza artesanal, ingredientes frescos, sabor incomparável.</p>
            <div class="hero-buttons">
                <a href="#contact" class="btn btn-primary">Reservar Mesa</a>
                <a href="#menu" class="btn btn-secondary">Ver Menu</a>
            </div>
        </div>
    </section>

    <!-- ABOUT -->
    <section class="about scroll-reveal" id="about">
        <div class="about-inner">
            <div class="about-image-wrapper">
                <img src="https://images.unsplash.com/photo-1579751626657-72bc17010498?w=900&q=90" alt="Chef" class="about-image">
                <div class="about-image-overlay">Desde 2010</div>
            </div>
            <div class="about-content">
                <h2>Paixão pela Autenticidade</h2>
                <p>Há mais de uma década, a Napoli Pizzaria tem sido sinónimo de excelência e tradição italiana em Tagus. Cada pizza é uma obra de arte, preparada com ingredientes cuidadosamente selecionados e receitas transmitidas através de gerações.</p>
                <p>O nosso forno a lenha tradicional, importado diretamente de Nápoles, garante aquela crosta perfeita e sabor inconfundível que nos distingue.</p>
                
                <div class="about-features">
                    <div class="feature">
                        <div class="feature-icon">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/></svg>
                        </div>
                        <h4>Ingredientes Premium</h4>
                        <p>Importados diretamente de Itália</p>
                    </div>
                    <div class="feature">
                        <div class="feature-icon">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/></svg>
                        </div>
                        <h4>Forno Tradicional</h4>
                        <p>Forno a lenha napolitano autêntico</p>
                    </div>
                    <div class="feature">
                        <div class="feature-icon">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/></svg>
                        </div>
                        <h4>Receitas Originais</h4>
                        <p>Tradição passada por gerações</p>
                    </div>
                    <div class="feature">
                        <div class="feature-icon">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/></svg>
                        </div>
                        <h4>Chefs Especializados</h4>
                        <p>Equipa treinada em Nápoles</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- TEAM -->
    <section class="team scroll-reveal" id="team">
        <div class="team-inner">
            <div class="team-header">
                <h2>A Nossa Equipa</h2>
                <p>Conheça os mestres por trás da magia culinária da Napoli Pizzaria.</p>
            </div>
            
            <div class="team-grid">
                <div class="team-card">
                    <div class="team-photo">
                        <img src="https://images.unsplash.com/photo-1577219491135-ce391730fb2c?w=600&q=90" alt="Chef Marco">
                        <div class="team-overlay">
                            <div class="team-social">
                                <a href="#"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg></a>
                                <a href="#"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg></a>
                            </div>
                        </div>
                    </div>
                    <h3>Chef Marco Rossi</h3>
                    <div class="role">Chef Executivo</div>
                    <p>30 anos de experiência, formado em Nápoles com passagem por restaurantes estrelados Michelin.</p>
                </div>

                <div class="team-card">
                    <div class="team-photo">
                        <img src="https://images.unsplash.com/photo-1583394293214-28ded15ee548?w=600&q=90" alt="Chef Sofia">
                        <div class="team-overlay">
                            <div class="team-social">
                                <a href="#"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg></a>
                                <a href="#"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg></a>
                            </div>
                        </div>
                    </div>
                    <h3>Sofia Bianchi</h3>
                    <div class="role">Sous Chef</div>
                    <p>Especialista em massas frescas e sobremesas tradicionais italianas.</p>
                </div>

                <div class="team-card">
                    <div class="team-photo">
                        <img src="https://images.unsplash.com/photo-1595273670150-bd0c3c392e46?w=600&q=90" alt="Pizzaiolo Luigi">
                        <div class="team-overlay">
                            <div class="team-social">
                                <a href="#"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg></a>
                                <a href="#"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg></a>
                            </div>
                        </div>
                    </div>
                    <h3>Luigi Romano</h3>
                    <div class="role">Pizzaiolo Mestre</div>
                    <p>Certificado pela AVPN, guardião das técnicas napolitanas autênticas.</p>
                </div>

                <div class="team-card">
                    <div class="team-photo">
                        <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=600&q=90" alt="Ana">
                        <div class="team-overlay">
                            <div class="team-social">
                                <a href="#"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg></a>
                                <a href="#"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg></a>
                            </div>
                        </div>
                    </div>
                    <h3>Ana Santos</h3>
                    <div class="role">Sommelier</div>
                    <p>Curadora de vinhos italianos e responsável pela experiência de harmonização.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- STATS -->
    <section class="stats scroll-reveal">
        <div class="stats-inner">
            <div class="stat-item">
                <div class="stat-number" data-target="15">0</div>
                <div class="stat-label">Anos de Tradição</div>
            </div>
            <div class="stat-item">
                <div class="stat-number" data-target="50000">0</div>
                <div class="stat-label">Pizzas Servidas</div>
            </div>
            <div class="stat-item">
                <div class="stat-number" data-target="247">0</div>
                <div class="stat-label">Avaliações 5★</div>
            </div>
            <div class="stat-item">
                <div class="stat-number" data-target="98">0</div>
                <div class="stat-label">% Satisfação</div>
            </div>
        </div>
    </section>

    <!-- MENU -->
    <section class="menu scroll-reveal" id="menu">
        <div class="menu-inner">
            <div class="menu-header">
                <h2>O Nosso Menu</h2>
                <p>Explore a nossa seleção de pratos autênticos italianos, preparados com ingredientes frescos e receitas tradicionais.</p>
            </div>
            
            <div class="menu-tabs">
                <button class="menu-tab active" data-category="pizzas">Pizzas</button>
                <button class="menu-tab" data-category="massas">Massas</button>
                <button class="menu-tab" data-category="bebidas">Bebidas</button>
                <button class="menu-tab" data-category="sobremesas">Sobremesas</button>
            </div>

            <div class="menu-content active" id="pizzas">
                <div class="menu-grid">
                    <div class="menu-card">
                        <div class="menu-card-image-wrapper">
                            <img src="https://images.unsplash.com/photo-1574071318508-1cdbab80d002?w=700&q=90" alt="Margherita">
                            <div class="menu-card-badge">Favorita</div>
                        </div>
                        <div class="menu-card-content">
                            <h3>Margherita</h3>
                            <span class="price">10.90€</span>
                            <p>Molho de tomate San Marzano, mozzarella di bufala, manjericão fresco.</p>
                        </div>
                    </div>
                    <div class="menu-card">
                        <div class="menu-card-image-wrapper">
                            <img src="https://images.unsplash.com/photo-1628840042765-356cda07504e?w=700&q=90" alt="Quattro Formaggi">
                        </div>
                        <div class="menu-card-content">
                            <h3>Quattro Formaggi</h3>
                            <span class="price">13.90€</span>
                            <p>Mozzarella, gorgonzola DOP, parmigiano reggiano, provolone piccante.</p>
                        </div>
                    </div>
                    <div class="menu-card">
                        <div class="menu-card-image-wrapper">
                            <img src="https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?w=700&q=90" alt="Diavola">
                            <div class="menu-card-badge">Picante</div>
                        </div>
                        <div class="menu-card-content">
                            <h3>Diavola</h3>
                            <span class="price">12.90€</span>
                            <p>Molho de tomate, mozzarella, salame calabrês piccante, pimentos frescos.</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="menu-content" id="massas">
                <div class="menu-grid">
                    <div class="menu-card">
                        <div class="menu-card-image-wrapper">
                            <img src="https://images.unsplash.com/photo-1621996346565-e3dbc646d9a9?w=700&q=90" alt="Carbonara">
                            <div class="menu-card-badge">Clássica</div>
                        </div>
                        <div class="menu-card-content">
                            <h3>Carbonara</h3>
                            <span class="price">12.90€</span>
                            <p>Guanciale, ovos, pecorino romano, pimenta preta.</p>
                        </div>
                    </div>
                    <div class="menu-card">
                        <div class="menu-card-image-wrapper">
                            <img src="https://images.unsplash.com/photo-1563379926898-05f4575a45d8?w=700&q=90" alt="Lasagna">
                        </div>
                        <div class="menu-card-content">
                            <h3>Lasagna</h3>
                            <span class="price">15.90€</span>
                            <p>Ragù de carne, bechamel, parmesão gratinado.</p>
                        </div>
                    </div>
                    <div class="menu-card">
                        <div class="menu-card-image-wrapper">
                            <img src="https://images.unsplash.com/photo-1612927601601-6638404737ce?w=700&q=90" alt="Arrabbiata">
                        </div>
                        <div class="menu-card-content">
                            <h3>Arrabbiata</h3>
                            <span class="price">10.90€</span>
                            <p>Molho picante, alho, malagueta.</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="menu-content" id="bebidas">
                <div class="menu-grid">
                    <div class="menu-card">
                        <div class="menu-card-image-wrapper">
                            <img src="https://images.unsplash.com/photo-1510591509098-f4fdc6d0ff04?w=700&q=90" alt="Vinho">
                        </div>
                        <div class="menu-card-content">
                            <h3>Chianti Classico</h3>
                            <span class="price">22.00€</span>
                            <p>Vinho tinto toscano encorpado.</p>
                        </div>
                    </div>
                    <div class="menu-card">
                        <div class="menu-card-image-wrapper">
                            <img src="https://images.unsplash.com/photo-1553361371-9b22f78e8b1d?w=700&q=90" alt="Prosecco">
                        </div>
                        <div class="menu-card-content">
                            <h3>Prosecco DOC</h3>
                            <span class="price">18.00€</span>
                            <p>Espumante italiano fresco.</p>
                        </div>
                    </div>
                    <div class="menu-card">
                        <div class="menu-card-image-wrapper">
                            <img src="https://images.unsplash.com/photo-1461023058943-07fcbe16d735?w=700&q=90" alt="Espresso">
                        </div>
                        <div class="menu-card-content">
                            <h3>Espresso</h3>
                            <span class="price">2.50€</span>
                            <p>Café expresso autêntico.</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="menu-content" id="sobremesas">
                <div class="menu-grid">
                    <div class="menu-card">
                        <div class="menu-card-image-wrapper">
                            <img src="https://images.unsplash.com/photo-1571877227200-a0d98ea607e9?w=700&q=90" alt="Tiramisu">
                            <div class="menu-card-badge">Top</div>
                        </div>
                        <div class="menu-card-content">
                            <h3>Tiramisù</h3>
                            <span class="price">6.90€</span>
                            <p>Mascarpone, café, cacau.</p>
                        </div>
                    </div>
                    <div class="menu-card">
                        <div class="menu-card-image-wrapper">
                            <img src="https://images.unsplash.com/photo-1563805042-7684c019e1cb?w=700&q=90" alt="Gelato">
                        </div>
                        <div class="menu-card-content">
                            <h3>Gelato</h3>
                            <span class="price">5.50€</span>
                            <p>3 bolas artesanais.</p>
                        </div>
                    </div>
                    <div class="menu-card">
                        <div class="menu-card-image-wrapper">
                            <img src="https://images.unsplash.com/photo-1488477181946-6428a0291777?w=700&q=90" alt="Panna Cotta">
                        </div>
                        <div class="menu-card-content">
                            <h3>Panna Cotta</h3>
                            <span class="price">5.90€</span>
                            <p>Sobremesa cremosa italiana.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- EXPERIENCE -->
    <section class="experience scroll-reveal">
        <div class="experience-inner">
            <div class="experience-header">
                <h2>O Que Nos Torna Únicos</h2>
                <p>Mais do que uma refeição, oferecemos uma viagem sensorial à autêntica Itália.</p>
            </div>
            
            <div class="experience-grid">
                <div class="experience-card">
                    <div class="experience-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 14.5c-2.49 0-4.5-2.01-4.5-4.5S9.51 7.5 12 7.5s4.5 2.01 4.5 4.5-2.01 4.5-4.5 4.5zm0-5.5c-.55 0-1 .45-1 1s.45 1 1 1 1-.45 1-1-.45-1-1-1z"/></svg>
                    </div>
                    <h3>Forno Tradicional</h3>
                    <p>Forno a lenha napolitano que atinge 485°C.</p>
                </div>
                <div class="experience-card">
                    <div class="experience-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zm-1-13h2v6h-2zm0 8h2v2h-2z"/></svg>
                    </div>
                    <h3>Massa Artesanal</h3>
                    <p>Fermentação natural de 48 horas.</p>
                </div>
                <div class="experience-card">
                    <div class="experience-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2l-5.5 9h11z"/><circle cx="17.5" cy="17.5" r="4.5"/><circle cx="5.5" cy="17.5" r="4.5"/></svg>
                    </div>
                    <h3>Ingredientes Italianos</h3>
                    <p>Produtos certificados DOP e IGP.</p>
                </div>
                <div class="experience-card">
                    <div class="experience-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg>
                    </div>
                    <h3>Mestres Pizzaiolos</h3>
                    <p>Equipa treinada em Nápoles.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- GALLERY -->
    <section class="gallery scroll-reveal">
        <div class="gallery-grid">
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?w=800&q=90" alt="1">
                <div class="gallery-overlay">Ambiente</div>
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1565299585323-38d6b0865b47?w=800&q=90" alt="2">
                <div class="gallery-overlay">Pizzas</div>
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1590534247854-e973a54d0f53?w=800&q=90" alt="3">
                <div class="gallery-overlay">Chefs</div>
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1555939594-58d7cb561ad1?w=800&q=90" alt="4">
                <div class="gallery-overlay">Experiência</div>
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1571407970349-bc81e7e96a47?w=800&q=90" alt="5">
                <div class="gallery-overlay">Detalhes</div>
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1574071318508-1cdbab80d002?w=800&q=90" alt="6">
                <div class="gallery-overlay">Tradição</div>
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1579751626657-72bc17010498?w=800&q=90" alt="7">
                <div class="gallery-overlay">Arte</div>
            </div>
            <div class="gallery-item">
                <img src="https://images.unsplash.com/photo-1593560708920-61dd98c46a4e?w=800&q=90" alt="8">
                <div class="gallery-overlay">Sabor</div>
            </div>
        </div>
    </section>

    <!-- TESTIMONIALS -->
    <section class="testimonials scroll-reveal" id="testimonials">
        <div class="testimonials-inner">
            <div class="testimonials-header">
                <h2>Avaliações Google</h2>
                <div class="google-rating">
                    <span class="google-logo">Google</span>
                    <span class="overall-rating">4.8</span>
                    <div class="stars-large">
                        <span>★</span>
                        <span>★</span>
                        <span>★</span>
                        <span>★</span>
                        <span>★</span>
                    </div>
                </div>
                <p class="review-count">Baseado em 247 avaliações</p>
            </div>
            
            <div class="reviews-carousel-container">
                <div class="reviews-carousel" id="reviewsCarousel">
                    <div class="review-card">
                        <div class="review-header">
                            <div class="reviewer-avatar">MC</div>
                            <div class="reviewer-info">
                                <h4>Maria Costa</h4>
                                <div class="review-stars">★★★★★</div>
                                <p class="review-date">Há 2 semanas</p>
                            </div>
                        </div>
                        <p class="review-text">"Sem dúvida a melhor pizza italiana que já provei em Portugal!"</p>
                        <div class="google-badge">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/></svg>
                            Publicado no Google
                        </div>
                    </div>
                    <div class="review-card">
                        <div class="review-header">
                            <div class="reviewer-avatar">RS</div>
                            <div class="reviewer-info">
                                <h4>Ricardo Silva</h4>
                                <div class="review-stars">★★★★★</div>
                                <p class="review-date">Há 1 mês</p>
                            </div>
                        </div>
                        <p class="review-text">"Ambiente familiar e acolhedor. Serviço impecável!"</p>
                        <div class="google-badge">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/></svg>
                            Publicado no Google
                        </div>
                    </div>
                    <div class="review-card">
                        <div class="review-header">
                            <div class="reviewer-avatar">AR</div>
                            <div class="reviewer-info">
                                <h4>Ana Rossi</h4>
                                <div class="review-stars">★★★★★</div>
                                <p class="review-date">Há 3 semanas</p>
                            </div>
                        </div>
                        <p class="review-text">"Autenticidade italiana genuína! Complimenti!"</p>
                        <div class="google-badge">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/></svg>
                            Publicado no Google
                        </div>
                    </div>
                    <div class="review-card">
                        <div class="review-header">
                            <div class="reviewer-avatar">PM</div>
                            <div class="reviewer-info">
                                <h4>Pedro Martins</h4>
                                <div class="review-stars">★★★★★</div>
                                <p class="review-date">Há 1 semana</p>
                            </div>
                        </div>
                        <p class="review-text">"Carbonara divinal! Voltarei com certeza!"</p>
                        <div class="google-badge">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/></svg>
                            Publicado no Google
                        </div>
                    </div>
                </div>
            </div>

            <div class="carousel-controls">
                <button class="carousel-btn" id="prevBtn">←</button>
                <button class="carousel-btn" id="nextBtn">→</button>
            </div>
        </div>
    </section>

    <!-- LOCATION -->
    <section class="location scroll-reveal" id="location">
        <div class="location-inner">
            <div class="location-header">
                <h2>Visite-nos em Tagus</h2>
            </div>
            
            <div class="location-grid">
                <div class="location-info">
                    <div>
                        <h3>Morada</h3>
                        <p>Rua Principal, 123<br>Tagus, Portugal<br>2000-000</p>
                    </div>
                    <div>
                        <h3>Horário</h3>
                        <p>Terça a Quinta: 12:00 - 23:00<br>Sexta e Sábado: 12:00 - 00:00<br>Domingo: 12:00 - 22:00<br>Segunda: Fechado</p>
                    </div>
                    <div>
                        <h3>Contactos</h3>
                        <p>Tel: +351 XXX XXX XXX<br>Email: info@napolipizzaria.pt</p>
                    </div>
                </div>
                <div class="location-map">
                    Google Maps
                </div>
            </div>
        </div>
    </section>

    <!-- CTA -->
    <section class="cta scroll-reveal" id="contact">
        <h2>Reserve a Sua Mesa</h2>
        <p>Garanta o seu lugar e desfrute de uma autêntica experiência italiana.</p>
        <div class="cta-buttons">
            <a href="tel:+351XXXXXXXXX" class="btn btn-white">Ligar para Reservar</a>
            <a href="mailto:reservas@napolipizzaria.pt" class="btn btn-secondary">Enviar Email</a>
        </div>
    </section>

    <!-- FOOTER -->
    <footer>
        <div class="footer-inner">
            <div class="footer-grid">
                <div class="footer-section">
                    <h3>Napoli Pizzaria</h3>
                    <p>Tradição italiana desde 2010.</p>
                </div>
                <div class="footer-section">
                    <h3>Links</h3>
                    <p>Sobre<br>Menu<br>Reservas</p>
                </div>
                <div class="footer-section">
                    <h3>Serviços</h3>
                    <p>Take Away<br>Delivery<br>Eventos</p>
                </div>
                <div class="footer-section">
                    <h3>Contacto</h3>
                    <p>Rua Principal, 123<br>Tagus<br>+351 XXX XXX XXX</p>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 Napoli Pizzaria. Website por João Alfar</p>
            </div>
        </div>
    </footer>

    <script>
        // Navbar scroll
        window.addEventListener('scroll', () => {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Scroll reveal
        const revealElements = document.querySelectorAll('.scroll-reveal');
        const revealOnScroll = () => {
            revealElements.forEach(el => {
                const elementTop = el.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                if (elementTop < windowHeight - 100) {
                    el.classList.add('active');
                }
            });
        };
        window.addEventListener('scroll', revealOnScroll);
        revealOnScroll();

        // Counter animation
        const animateCounter = (element) => {
            const target = parseInt(element.getAttribute('data-target'));
            const duration = 2000;
            const step = target / (duration / 16);
            let current = 0;
            
            const updateCounter = () => {
                current += step;
                if (current < target) {
                    element.textContent = Math.floor(current).toLocaleString();
                    requestAnimationFrame(updateCounter);
                } else {
                    element.textContent = target.toLocaleString();
                }
            };
            updateCounter();
        };

        const statItems = document.querySelectorAll('.stat-item');
        const statsObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                    const number = entry.target.querySelector('.stat-number');
                    animateCounter(number);
                    statsObserver.unobserve(entry.target);
                }
            });
        });
        statItems.forEach(item => statsObserver.observe(item));

        // Menu tabs
        const menuTabs = document.querySelectorAll('.menu-tab');
        const menuContents = document.querySelectorAll('.menu-content');
        menuTabs.forEach(tab => {
            tab.addEventListener('click', () => {
                menuTabs.forEach(t => t.classList.remove('active'));
                menuContents.forEach(c => c.classList.remove('active'));
                tab.classList.add('active');
                document.getElementById(tab.getAttribute('data-category')).classList.add('active');
            });
        });

        // Reviews carousel
        const carousel = document.getElementById('reviewsCarousel');
        const prevBtn = document.getElementById('prevBtn');
        const nextBtn = document.getElementById('nextBtn');
        let currentIndex = 0;
        const cardsToShow = window.innerWidth > 968 ? 3 : (window.innerWidth > 640 ? 2 : 1);
        const totalCards = document.querySelectorAll('.review-card').length;
        const maxIndex = totalCards - cardsToShow;

        function updateCarousel() {
            const cardWidth = document.querySelector('.review-card').offsetWidth;
            const gap = 32;
            const offset = -(currentIndex * (cardWidth + gap));
            carousel.style.transform = `translateX(${offset}px)`;
            prevBtn.disabled = currentIndex === 0;
            nextBtn.disabled = currentIndex >= maxIndex;
        }

        prevBtn.addEventListener('click', () => {
            if (currentIndex > 0) {
                currentIndex--;
                updateCarousel();
            }
        });

        nextBtn.addEventListener('click', () => {
            if (currentIndex < maxIndex) {
                currentIndex++;
                updateCarousel();
            }
        });

        window.addEventListener('resize', () => {
            currentIndex = 0;
            updateCarousel();
        });

        updateCarousel();
    </script>

</body>
</html>
