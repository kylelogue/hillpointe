<script lang="ts" setup>
const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  });
};
</script>

<template>
  <footer class="footer">
    <div class="footer-main">
      <div class="footer-container">
        
        <!-- Company Info -->
        <div class="footer-section company-info">
          <div class="logo">
            <div class="logo-icon">H</div>
            <span class="logo-text">HILLPOINTE</span>
          </div>
          <div class="contact-info">
            <a
              href="mailto:info@hillpointe.com"
              class="contact-link"
            >
              info@hillpointe.com
            </a>
            <a
              href="tel:407.752.9004"
              class="contact-link"
            >
              407.752.9004
            </a>
          </div>
          <div class="social-links">
            <a
              href="#"
              class="social-link"
              aria-label="Instagram"
            >
              <svg
                width="20"
                height="20"
                viewBox="0 0 24 24"
                fill="currentColor"
              >
                <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
              </svg>
            </a>
            <a
              href="#"
              class="social-link"
              aria-label="LinkedIn"
            >
              <svg
                width="20"
                height="20"
                viewBox="0 0 24 24"
                fill="currentColor"
              >
                <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
              </svg>
            </a>
          </div>
        </div>

        <!-- Office Locations -->
        <div class="footer-section offices">
          <div class="office-group">
            <h3 class="office-title">Corporate Headquarters</h3>
            <div class="office-details">
              <p>631 W Morse Blvd., Suite 200</p>
              <p>Winter Park, FL 32789</p>
            </div>
          </div>

          <div class="office-group">
            <h3 class="office-title">Operations Offices</h3>
            <div class="office-details">
              <div class="office-location">
                <p>8830 Macon Hwy., Building 300</p>
                <p>Athens, GA 30606</p>
              </div>
              <div class="office-location">
                <p>165 Ottley Dr., Suite 205</p>
                <p>Atlanta, GA 30324</p>
              </div>
              <div class="office-location">
                <p>1910 South Blvd., Suite 220</p>
                <p>Charlotte, NC 28203</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Awards -->
        <div class="footer-section awards">
          <div class="award">
            <img 
              src="@/assets/images/nmhc-top-builders-2025.png" 
              alt="NMHC 2025 Top 50 Builders Award"
              class="award-image"
            />
          </div>
          <div class="award">
            <img 
              src="@/assets/images/nmhc-top-developers-2025.png" 
              alt="NMHC 2025 Top 50 Developers Award"
              class="award-image"
            />
          </div>
        </div>

      </div>
    </div>

    <!-- Copyright Bar -->
    <div class="footer-bottom">
      <div class="footer-container">
        <div class="copyright-content">
          <span>Copyright © 2025 Hillpointe All Rights Reserved.</span>
          <a
            href="#"
            class="legal-link"
          >Legal Disclaimer</a>
        </div>
        <button
          class="scroll-top"
          @click="scrollToTop"
          aria-label="Scroll to top"
        >
          <svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="currentColor"
          >
            <path d="M7.41 15.41L12 10.83l4.59 4.58L18 14l-6-6-6 6z"/>
          </svg>
        </button>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.footer {
  background: linear-gradient(135deg, #357ABD 0%, #2968A3 100%);
  color: white;
  font-family: 'Lato', sans-serif;
}

.footer-main {
  padding: 60px 0 40px;
}

.footer-container {
  max-width: 1600px;
  margin: 0 auto;
  padding: 0 45px;
}

.footer-main .footer-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 60px;
  align-items: start;
}

.footer-section {
  &.company-info {
    .logo {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 24px;

      .logo-icon {
        width: 40px;
        height: 40px;
        background: white;
        color: #357ABD;
        display: flex;
        align-items: center;
        justify-content: center;
        font-family: 'Montserrat', sans-serif;
        font-weight: 700;
        font-size: 24px;
        border-radius: 4px;
      }

      .logo-text {
        font-family: 'Montserrat', sans-serif;
        font-weight: 600;
        font-size: 24px;
        letter-spacing: 1px;
      }
    }

    .contact-info {
      display: flex;
      flex-direction: column;
      gap: 8px;
      margin-bottom: 24px;

      .contact-link {
        color: rgba(255, 255, 255, 0.9);
        text-decoration: none;
        font-size: 16px;
        transition: color 0.2s ease;

        &:hover {
          color: white;
        }
      }
    }

    .social-links {
      display: flex;
      gap: 16px;

      .social-link {
        color: rgba(255, 255, 255, 0.8);
        transition: color 0.2s ease;

        &:hover {
          color: white;
        }
      }
    }
  }

  &.offices {
    .office-group {
      margin-bottom: 32px;

      &:last-child {
        margin-bottom: 0;
      }

      .office-title {
        font-family: 'Montserrat', sans-serif;
        font-weight: 600;
        font-size: 18px;
        margin-bottom: 16px;
        color: white;
      }

      .office-details {
        color: rgba(255, 255, 255, 0.9);
        line-height: 1.6;

        .office-location {
          margin-bottom: 16px;

          &:last-child {
            margin-bottom: 0;
          }
        }

        p {
          margin: 0 0 4px 0;
          font-size: 15px;
        }
      }
    }
  }

  &.awards {
    display: flex;
    flex-direction: column;
    gap: 24px;

    .award {
      .award-image {
        width: 100%;
        max-width: 150px;
        height: auto;
        transition: transform 0.2s ease;

        &:hover {
          transform: scale(1.05);
        }
      }
    }
  }
}

.footer-bottom {
  background: rgba(0, 0, 0, 0.2);
  padding: 20px 0;

  .footer-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .copyright-content {
    display: flex;
    align-items: center;
    gap: 24px;
    font-size: 14px;
    color: rgba(255, 255, 255, 0.8);

    .legal-link {
      color: rgba(255, 255, 255, 0.8);
      text-decoration: none;
      transition: color 0.2s ease;

      &:hover {
        color: white;
      }
    }
  }

  .scroll-top {
    background: rgba(255, 255, 255, 0.1);
    border: none;
    color: white;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: background 0.2s ease;

    &:hover {
      background: rgba(255, 255, 255, 0.2);
    }
  }
}

// Responsive Design
@media (max-width: 1024px) {
  .footer-main .footer-container {
    grid-template-columns: 1fr;
    gap: 40px;
    text-align: center;
  }

  .footer-section.offices {
    .office-group {
      .office-details {
        .office-location {
          margin-bottom: 24px;
        }
      }
    }
  }

  .footer-section.awards {
    flex-direction: row;
    justify-content: center;
  }
}

@media (max-width: 768px) {
  .footer-container {
    padding: 0 24px !important;
  }

  .footer-main {
    padding: 40px 0 30px;
  }

  .footer-bottom .footer-container {
    flex-direction: column;
    gap: 16px;
  }

  .copyright-content {
    flex-direction: column;
    gap: 8px !important;
    text-align: center;
  }

  .footer-section.awards {
    flex-direction: column;
    align-items: center;
  }
}
</style>