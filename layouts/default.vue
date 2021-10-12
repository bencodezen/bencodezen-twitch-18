<template>
  <div>
    <MainNav />
    <slot name="header">
      <h2>My Default header</h2>
    </slot>
    <slot name="default" />
    <slot name="footer">
      <footer>Copyright {{ new Date().getFullYear() }}</footer>
    </slot>
  </div>
</template>
