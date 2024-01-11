<template>
  <div class="main">
    <div class="container1 animate__animated animate__slideInLeft">
      <img src="https://i.postimg.cc/pL8zc0vV/IMG-20231225-100757.png" alt="Professional Image">
      <h3>Haanim Pietersen</h3>
      <p>Aspiring Software Developer</p>
      <p><strong>Address:</strong><br>20 Broadbill Street, Pelican Park</p>
      <p><strong>Phone Number:</strong><br>071 433 2419</p>
      <p><strong>Email:</strong><br>haanimpietersen@gmail.com</p>
    </div>
    <div class="container2 animate__animated animate__slideInRight">
      <h1>About Me</h1>
      <p>Hello,<br><br>

I'm Haanim, a dedicated student at Life Choices Coding Academy, having graduated from South Peninsula High School in 2022. Passionate about coding, I thrive in both independent and collaborative learning environments, embodying a strong work ethic.<br><br>

Beyond coding, I'm an avid learner exploring diverse subjects, fostering a well-rounded perspective. I value meaningful connections, seeking personal and professional growth through understanding and collaboration.<br><br>

Navigating the dynamic landscape of work and learning, I look forward to expanding my knowledge, building lasting connections, and contributing to positive change.<br><br>

Best regards,
Haanim Pietersen
      </p>
    </div>
  </div>
</template>

<script>
import 'animate.css';
export default {
  // Your component options here
};
</script>


<style scoped>
.main {
  display: flex;
  background: #80553C;
  padding: 20px;
}

.container1 {
  width: 40%;
  color: #D2B48C;
  background: #664229;
  padding: 20px;
  text-align: center;
  border-radius: 10px;
  margin-right: 20px;
}

.container1 img {
  height: 5rem;
  border-radius: 50%;
}

.container1 h3 {
  font-weight: bold;
  margin-top: 10px;
}

.container1 p {
  margin: 5px 0;
}

.container2 {
  width: 60%;
  color: #664229;
  background: #D2B48C;
  padding: 20px;
  border-radius: 10px;
}

.container2 h1 {
  font-weight: bold;
  margin-bottom: 10px;
}

@media (max-width: 767px) {
  .main {
    flex-direction: column;
  }

  .container1,
  .container2 {
    width: 100%;
  }
}

@media (min-width: 768px) and (max-width: 1024px) {
  .main {
    flex-direction: row;
  }

  .container1 {
    width: 40%;
    margin-bottom: 0;
  }

  .container2 {
    width: 60%;
  }
}

@media (min-width: 1025px) {
  .container1 {
    width: 30%;
  }

  .container2 {
    width: 70%;
  }
}
</style>