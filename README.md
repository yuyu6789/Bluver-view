# Bluver-view
import axios from 'axios';

const api = axios.create({
    baseURL: 'http://localhost:3000'
});

// Example usage
api.get('/posts').then(response => {
    console.log(response.data);
});
