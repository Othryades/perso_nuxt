<template>
        <section>
        <div class="form-submit">
            <h2 class="subtitle">submit</h2>
            <form  target="_blank" action="https://formsubmit.co/3c6be1936fe745bd474914c31dce33a7" method="POST">
                <input type="hidden" name="_captcha" value="false">
                <input type="hidden" name="_next" value="https://ania-kubow.com/src/pages/thankyou.html">
                <div class="form-row">
                    <input name="name" class="form-control" placeholder="Full Name" required>
                    <input name="email" class="form-control" placeholder="Email" required>
                </div>
                <textarea placeholder="Your Message" name="message" rows="10" required></textarea>
                <button type="submit">Submit Form</button>
            </form>
        </div>
    </section>
</template>

<style>
section {
    display: flex;
    flex-direction: column;
    align-items: center;
}
h2 {
    margin: 3px;
    font-weight: 300;
    text-align: center;
}
.form-submit {
    width: 50%;
}

.form-submit form {
    width: 100%;
}

.form-submit .form-row {
    display: flex;
    justify-content: space-between;
}

.form-row .form-control {
    width: 50%;
    border: none;
    font-size: 20px;
    padding: 5px;
    font-family: 'Josefin Sans', sans-serif;
    padding: 20px 0;
}

.form-row .form-control:focus,
.form-submit textarea:focus {
    outline: 0;
    /* background-color: yellow; */
}

.form-submit textarea {
    color: black;
    font-family: 'Josefin Sans', sans-serif;
    width: 100%;
    border: none;
    padding: 0;
    resize: none;
    margin-top: 5px;
    font-size: 20px;
    padding: 20px 0;
}

form button {
    width: 100%;
    background-color: rgb(79,177,79);
    color: rgb(255,255,255);
    border: none;
    font-family: 'Josefin Sans', sans-serif;
    padding: 20px;
    font-size: 20px;
}

@media only screen and (max-width: 600px) {
    .form-submit {
        width: 80%;
    }

    .form-submit .form-row {
        display: flex;
        flex-direction: column;
    }

    .form-row .form-control {
        width: 100%;
        margin-top: 5px;
    }
}

</style>
