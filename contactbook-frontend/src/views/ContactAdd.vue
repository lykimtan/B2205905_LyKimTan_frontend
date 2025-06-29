<template>
    <div class="page">
        <h4>Thêm liên hệ</h4>
        <ContactForm
        :contact="contact"
        @submit:contact="createContact"
        />
        <p>{{ message }}</p>
    </div>
</template>

<script>
    import ContactForm from '@/components/ContactForm.vue';
    import contactService from '@/services/contact.service';

    export default {
        components: {
            ContactForm,
        },

        data() {
            return {
                contact: {
                name: "",
                email: "",
                address: "",
                phone: "",
                favorite: false,
                },
                message: "",
            };
        },

        methods: {  
            async createContact(data) {
                try {
                    await contactService.create(data);
                    alert("Liên hệ đã được thêm thành công.");
                    this.$router.push({ name: "contactbook"});
                }
                catch(error) {
                    console.log(error);
                }
            },

        },

        created() {
            this.message = '';
        },
    };
</script>