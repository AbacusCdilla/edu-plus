<template>
  <div>
    <h2>Available Lessons</h2>
    <label for="sort">Sort by:</label>
    <select v-model="sortKey" @change="sortLessons">
      <option value="subject">Subject</option>
      <option value="location">Location</option>
      <option value="price">Price</option>
      <option value="spaces">Spaces</option>
    </select>
    <ul>
      <li v-for="lesson in sortedLessons" :key="lesson.id">
        <i :class="lesson.icon"></i> <!-- Font Awesome icon -->
        <span>{{ lesson.subject }}</span> - 
        <span>{{ lesson.location }}</span> - 
        <span>{{ lesson.price }}$</span> - 
        <span>{{ lesson.spaces }} spaces available</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lessons: [
        { id: 1, subject: 'Mathematics', location: 'Hendon', price: 100, spaces: 5, icon: 'fas fa-calculator' },
        { id: 2, subject: 'Science', location: 'Colindale', price: 80, spaces: 2, icon: 'fas fa-flask' },
        { id: 3, subject: 'History', location: 'Brent Cross', price: 90, spaces: 6, icon: 'fas fa-book' },
        { id: 4, subject: 'Art', location: 'Golders Green', price: 95, spaces: 7, icon: 'fas fa-paint-brush' },
        { id: 5, subject: 'Geography', location: 'Hendon', price: 85, spaces: 0, icon: 'fas fa-globe' },
        { id: 6, subject: 'Physics', location: 'Hendon', price: 110, spaces: 3, icon: 'fas fa-atom' },
        { id: 7, subject: 'Chemistry', location: 'Colindale', price: 75, spaces: 4, icon: 'fas fa-vial' },
        { id: 8, subject: 'Biology', location: 'Brent Cross', price: 95, spaces: 2, icon: 'fas fa-leaf' },
        { id: 9, subject: 'Literature', location: 'Golders Green', price: 80, spaces: 5, icon: 'fas fa-pen-alt' },
        { id: 10, subject: 'Computer Science', location: 'Hendon', price: 120, spaces: 1, icon: 'fas fa-laptop-code' },
      ],
      sortKey: 'subject' // Default sort key
    };
  },
  computed: {
    sortedLessons() {
      return this.lessons.sort((a, b) => {
        if (this.sortKey === 'price' || this.sortKey === 'spaces') {
          return a[this.sortKey] - b[this.sortKey];
        }
        return a[this.sortKey].localeCompare(b[this.sortKey]);
      });
    }
  },
  methods: {
    sortLessons() {
      // This method is triggered when the sort option changes
      // The computed property 'sortedLessons' will automatically update
    }
  }
}
</script>

<style scoped>
/* Styles specific to LessonList */
</style>