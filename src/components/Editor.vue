<template>
    <ckeditor
        v-model="data"
        :editor="ClassicEditor"
        :config="config"
    />
</template>

<script setup>
import { ref, computed } from 'vue';
import { ClassicEditor, Essentials, Paragraph, Bold, Italic } from 'ckeditor5';
import { FormatPainter } from 'ckeditor5-premium-features';
import { Ckeditor } from '@ckeditor/ckeditor5-vue';

import 'ckeditor5/ckeditor5.css';
import 'ckeditor5-premium-features/ckeditor5-premium-features.css';

const data = ref( '<p>Hello world!</p>' );

const config = computed( () => {
    return {
        licenseKey: 'eyJhbGciOiJFUzI1NiJ9.eyJleHAiOjE3NTgwNjcxOTksImp0aSI6IjEzZTE0ODc1LTJmZjMtNDkxOS05MThhLTEwZDk2YmYwYmNiZCIsInVzYWdlRW5kcG9pbnQiOiJodHRwczovL3Byb3h5LWV2ZW50LmNrZWRpdG9yLmNvbSIsImRpc3RyaWJ1dGlvbkNoYW5uZWwiOlsiY2xvdWQiLCJkcnVwYWwiLCJzaCJdLCJ3aGl0ZUxhYmVsIjp0cnVlLCJsaWNlbnNlVHlwZSI6InRyaWFsIiwiZmVhdHVyZXMiOlsiKiJdLCJ2YyI6IjdiNGY0ZjI4In0.AIm1AbHx7ZfHPW92VSRQ2wcI7ChVsGBX19hfRTcPE0F3rl5gKJI_PUKYZbL4XOHUMYVRzBqiIsJcstn8-D8xfw', // Or 'GPL'.
        plugins: [ Essentials, Paragraph, Bold, Italic, FormatPainter ],
        toolbar: [ 'undo', 'redo', '|', 'bold', 'italic', '|', 'formatPainter' ]
    };
} );
</script>
