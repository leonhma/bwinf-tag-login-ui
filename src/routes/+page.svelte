<script lang="ts">
    import '$lib/static/reset.css'
    import TextField from '@smui/textfield'
    import Button from '@smui/button'
    import IconButton, {Icon} from "@smui/icon-button";

    let username = "hi";
    let password = "correct horse battery staple";
    let showPassword = false;
</script>

<div id="login-card">
    <TextField variant='outlined' bind:value={username} label="Username" />
    <TextField variant='outlined' input$type={showPassword ? 'text' : 'password'} bind:value={password} label="Password">
        <svelte:fragment slot="trailingIcon">
            <IconButton toggle on:click={() => showPassword = !showPassword}>
                <Icon class="material-icons" off>visibility</Icon>
                <Icon class="material-icons" on>visibility_off</Icon>
            </IconButton>
        </svelte:fragment>
    </TextField>
    <div id="forgot">
        <Button size={3}>Forgot password?</Button>
    </div>
    <Button variant='raised'>Log in</Button>
    <div id="signup">
        Need an account? <Button size={3}>Sign up</Button>
    </div>
</div>

<style lang="scss">
    :root {
        background-image:url('https://picsum.photos/1000/1000?blur');
        font-family: Roboto, Arial, Helvetica, sans-serif
    }
    #login-card {
        padding: 2em;
        box-sizing: border-box;
        background: white;
        position: absolute;
        top: 50%;
        left: 50%;
        transform:translate(-50%, -50%);
        width: min(max(400px, 20vw), 100vw);
        height: auto;
        border-radius: 20px;
        box-shadow: 3 3;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 1em;
    }
    #forgot {
        align-self: flex-start;
    }
</style>
