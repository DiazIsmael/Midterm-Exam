<template>
  <div>
    <!-- Nav bar -->
    <nav class="navbar navbar-expand navbar-light bg-light">
      <div class="container">
        <a class="navbar-brand float-left" href="/">CIS 4339 Midterm</a>
        <ul class="nav navbar-nav mr-auto">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/form">Form</router-link>
          </li>
        </ul>
      </div>
    </nav>

    <!-- Router view - our main view below the navigation -->
    <div class="container mt-5">
      <RouterView></RouterView>
    </div>
  </div>
</template>


