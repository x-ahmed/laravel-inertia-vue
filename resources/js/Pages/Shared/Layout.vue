<template>
    <main>
        <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
            <a class="navbar-brand" href="#">Navbar</a>
            <button
                class="navbar-toggler"
                type="button"
                data-toggle="collapse"
                data-target="#navbarNav"
                aria-controls="navbarNav"
                aria-expanded="false"
                aria-label="Toggle navigation"
            >
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <div class="navbar-nav">
                    <inertia-link class="nav-item nav-link" href="/"
                        >Home</inertia-link
                    >
                    <inertia-link class="nav-item nav-link" href="/about"
                        >About</inertia-link
                    >
                    <inertia-link class="nav-item nav-link" href="/contact"
                        >Contact</inertia-link
                    >
                </div>
            </div>
        </nav>

        <article>
            <div class="container my-3">
                <div
                    v-if="$page.props.flash.message && $page.props.flash.type === 'success'"
                    class="alert alert-success"
                >
                    {{ $page.props.flash.message }}
                </div>
                <div
                    v-if="$page.props.flash.message && $page.props.flash.type === 'danger'"
                    class="alert alert-danger"
                >
                    {{ $page.props.flash.message }}
                </div>
                <slot />
            </div>
        </article>
    </main>
</template>
