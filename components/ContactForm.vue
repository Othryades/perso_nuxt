<template>
    <section class="contact-section">
        <div class="form-container">
            <h2 class="title">Let's Connect</h2>
            <p class="subtitle">Have a question or want to work together?</p>
            
            <form 
                ref="form"
                action="https://formsubmit.co/df1678e898c7849cbf7b26ec79b33fac" 
                method="POST"
                @submit="handleSubmit"
            >
                <input type="hidden" name="_captcha" value="false">
                <input type="hidden" name="_next" value="https://moris-dev.surge.sh/thankyou">
                <input type="hidden" name="_format" value="json">
                
                <div class="form-group">
                    <label for="name">Name</label>
                    <input 
                        id="name"
                        name="name" 
                        class="form-control" 
                        placeholder="Your name" 
                        required
                        :disabled="isLoading"
                        v-model="formData.name"
                    >
                </div>
                
                <div class="form-group">
                    <label for="email">Email</label>
                    <input 
                        id="email"
                        name="email" 
                        type="email"
                        class="form-control" 
                        placeholder="your.email@example.com" 
                        required
                        :disabled="isLoading"
                        v-model="formData.email"
                    >
                </div>
                
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea 
                        id="message"
                        name="message" 
                        rows="5" 
                        class="form-control"
                        placeholder="Your message here..." 
                        required
                        :disabled="isLoading"
                        v-model="formData.message"
                    ></textarea>
                </div>

                <button type="submit" class="submit-button" :disabled="isLoading">
                    <span v-if="!isLoading" class="button-content">
                        <span>Send Message</span>
                        <svg class="send-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor">
                            <path d="M22 2L11 13M22 2L15 22L11 13L2 9L22 2Z" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                    </span>
                    <span v-else class="loading-spinner"></span>
                </button>

                <div v-if="submitStatus" :class="['submit-status', submitStatus.type]">
                    {{ submitStatus.message }}
                </div>
            </form>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            isLoading: false,
            submitStatus: null,
            formData: {
                name: '',
                email: '',
                message: ''
            }
        }
    },
    methods: {
        handleSubmit(e) {
            this.isLoading = true
            this.submitStatus = null

            setTimeout(() => {
                this.isLoading = false
                this.submitStatus = {
                    type: 'success',
                    message: 'Message sent successfully! I will get back to you soon.'
                }
                this.formData = { name: '', email: '', message: '' }
            }, 2000)

            return true
        }
    }
}
</script>

<style>
.contact-section {
    min-height: calc(100vh - 200px);
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 2rem;
}

.form-container {
    width: 100%;
    max-width: 600px;
    background-color: var(--color-surface);
    padding: 2.5rem;
    border-radius: 1rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
}

.title {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 2rem;
    font-weight: 700;
    color: var(--color-text);
    margin-bottom: 0.5rem;
    letter-spacing: -0.02em;
}

.subtitle {
    color: var(--color-text-secondary);
    font-size: 1.1rem;
    margin-bottom: 2rem;
}

.form-group {
    margin-bottom: 1.5rem;
}

label {
    display: block;
    font-size: 0.875rem;
    font-weight: 500;
    color: var(--color-text);
    margin-bottom: 0.5rem;
}

.form-control {
    width: 100%;
    padding: 0.75rem 1rem;
    font-size: 1rem;
    line-height: 1.5;
    color: var(--color-text);
    background-color: var(--color-bg);
    border: 2px solid var(--color-surface);
    border-radius: 0.5rem;
    transition: all 0.3s ease;
}

.form-control:focus {
    outline: none;
    border-color: var(--color-accent);
    box-shadow: 0 0 0 3px rgba(0, 255, 157, 0.1);
}

.form-control::placeholder {
    color: var(--color-text-secondary);
    opacity: 0.7;
}

textarea.form-control {
    resize: vertical;
    min-height: 120px;
}

.submit-button {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    width: 100%;
    padding: 0.875rem 1.5rem;
    font-size: 1rem;
    font-weight: 500;
    color: var(--color-bg);
    background-color: var(--color-accent);
    border: none;
    border-radius: 0.5rem;
    cursor: pointer;
    transition: all 0.3s ease;
}

.submit-button:hover {
    background-color: var(--color-accent-hover);
    transform: translateY(-1px);
}

.submit-button:active {
    transform: translateY(0);
}

.button-content {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.35rem;
}

.send-icon {
    width: 16px;
    height: 16px;
    transition: transform 0.3s ease;
    margin-top: 1px;
}

.submit-button:hover .send-icon {
    transform: translateX(4px);
}

@media only screen and (max-width: 600px) {
    .contact-section {
        padding: 1rem;
        min-height: calc(100vh - 150px);
    }

    .form-container {
        padding: 1.5rem;
    }

    .title {
        font-size: 1.75rem;
    }

    .subtitle {
        font-size: 1rem;
    }

    .form-control {
        font-size: 0.875rem;
    }
}

.form-loading .form-control {
    opacity: 0.7;
    cursor: not-allowed;
}

.submit-button:disabled {
    opacity: 0.7;
    cursor: not-allowed;
    transform: none !important;
}

.loading-spinner {
    display: inline-block;
    width: 20px;
    height: 20px;
    border: 2px solid rgba(255, 255, 255, 0.3);
    border-radius: 50%;
    border-top-color: #fff;
    animation: spin 0.8s linear infinite;
}

@keyframes spin {
    to { transform: rotate(360deg); }
}

.submit-status {
    margin-top: 1rem;
    padding: 1rem;
    border-radius: 0.5rem;
    text-align: center;
    font-size: 0.875rem;
}

.submit-status.success {
    background-color: rgba(0, 255, 157, 0.1);
    color: var(--color-accent);
}

.submit-status.error {
    background-color: rgba(255, 0, 0, 0.1);
    color: #ff4444;
}
</style>
