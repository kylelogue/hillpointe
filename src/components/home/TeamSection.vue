<script lang="ts" setup>
import kellyMahoneyImage from '@/assets/images/kelly-mahoney.jpg';
import stevenCampisiImage from '@/assets/images/steven-campisi.jpg';

interface TeamMember {
  id: number;
  name: string;
  title: string;
  description: string;
  imagePath: string;
}

const teamMembers: TeamMember[] = [
  {
    id: 1,
    name: 'KELLY MAHONEY',
    title: 'Co-Founder + Managing Partner',
    description: 'Kelly heads the firm\'s development and construction efforts and is jointly responsible for the firm\'s new project origination, pre-development, project underwriting and asset management activities.',
    imagePath: kellyMahoneyImage,
  },
  {
    id: 2,
    name: 'STEVEN CAMPISI, CFA',
    title: 'Co-Founder + Managing Partner', 
    description: 'Steven heads the firm\'s capital markets and investor relations efforts and is jointly responsible for the firm\'s new project origination, pre-development, project underwriting, and asset management activities.',
    imagePath: stevenCampisiImage,
  },
];
</script>

<template>
  <section class="team-section">
    <div class="container">
      <div class="team-grid">
        <div 
          v-for="member in teamMembers" 
          :key="member.id" 
          class="team-member"
        >
          <div class="member-image">
            <img 
              :src="member.imagePath" 
              :alt="`${member.name} - ${member.title}`"
              class="profile-image"
            />
          </div>
          <div class="member-info">
            <h3 class="member-name">{{ member.name }}</h3>
            <p class="member-title">{{ member.title }}</p>
            <p class="member-description">{{ member.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.team-section {
  padding: 80px 0;
  background: #FFFFFF;
}

.container {
  max-width: 1600px;
  margin: 0 auto;
  padding: 0 45px;
}

.team-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: start;
}

.team-member {
  background: white;
  // border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  transition: transform 0.3s ease, box-shadow 0.3s ease;

  &:hover {
    transform: translateY(-8px);
    box-shadow: 0 8px 30px rgba(0, 0, 0, 0.12);
  }

  .member-image {
    width: 100%;
    height: 650px;
    overflow: hidden;

    .profile-image {
      width: 100%;
      height: 100%;
      object-fit: cover;
      object-position: center top;
    }
  }

  .member-info {
    padding: 32px;

    .member-name {
      color: #5CA4E9;
      font-size: 28px;
      font-weight: 700;
      margin: 0 0 8px 0;
      letter-spacing: 1px;
    }

    .member-title {
      color: #666;
      font-size: 16px;
      font-weight: 500;
      margin: 0 0 20px 0;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }

    .member-description {
      color: #333;
      font-size: 16px;
      line-height: 1.6;
      margin: 0;
    }
  }
}

// Responsive Design
@media (max-width: 1024px) {
  .team-grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .container {
    padding: 0 24px;
  }
}

@media (max-width: 768px) {
  .team-section {
    padding: 60px 0;
  }

  .team-member {
    .member-image {
      height: 300px;
    }

    .member-info {
      padding: 24px;

      .member-name {
        font-size: 24px;
      }

      .member-title {
        font-size: 14px;
      }

      .member-description {
        font-size: 15px;
      }
    }
  }
}
</style>