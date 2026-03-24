<template>
    <div class="item-slot">
        <div class="bucket-container">
            <img v-if="item.startsWith('minecraft:')"
                 :src="'https://coolerpromc.com/minecraft/item/' + item.replaceAll(':','__') + '.png'"
            >
            <img v-else-if="item !== ''"
                 :src="getImageSrc(item)">

            <!-- Output Count -->
            <div v-if="output_count != null"
                 class="output-count"
                 :class="output_count > 9 ? 'multi-digit' : 'single-digit'">
                <p class="minecraft-font">{{ output_count }}</p>
            </div>

            <!-- Tooltip -->
            <div v-if="item !== ''" class="tooltip">
                <p>{{ item.replaceAll('minecraft:', '').replaceAll('mod:', '').replace(/_/g, ' ').replace(/\b\w/g, l => l.toUpperCase()) }}</p>
            </div>
        </div>
    </div>
</template>

<script setup>
const images = import.meta.glob('../public/textures/*.png', { eager: true });

const getImageSrc = (item) => {
    const fileName = item.replaceAll('mod:', '') + '.png';
    return images[`../public/textures/${fileName}`]?.default || '';
};
</script>

<script>
export default {
    props: ['item', 'output_count'],
}
</script>

<style scoped>
.vp-doc img {
    margin: 0;
}
/* Base slot styling */
.item-slot {
    position: relative;
    width: 2.5rem;
    height: 2.5rem;
    background-color: #8B8B8B;
    border: 2px solid #FFFFFF;
    border-top-color: #373737;
    border-left-color: #373737;
}

.item-slot .bucket-container {
    position: relative;
}

.item-slot img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}

/* Output count positioning */
.item-slot .output-count {
    position: absolute;
    inset: 0;
}

.item-slot .output-count.single-digit {
    left: 1.5rem;
    right: 1.5rem;
}

.item-slot .output-count.multi-digit {
    left: 0.75rem;
    right: 0.75rem;
}

.item-slot .output-count p {
    font-size: 1.25rem;
    line-height: 1.75rem;
}

/* Tooltip */
.item-slot .tooltip {
    position: absolute;
    bottom: 100%;
    left: 50%;
    transform: translateX(-50%);
    margin-bottom: 0.5rem;
    display: none;
    background-color: #374151;
    color: white;
    font-size: 0.75rem;
    line-height: 1rem;
    border-radius: 0.25rem;
    padding: 0 0.5rem;
    white-space: nowrap;
}

.item-slot:hover .tooltip {
    display: block;
}

/* Responsive breakpoints */
/* xs breakpoint (475px and up) */
@media (min-width: 475px) {
    .item-slot {
        width: 3rem;
        height: 3rem;
    }

    .item-slot .output-count {
        top: 1.25rem;
        bottom: 1.25rem;
    }

    .item-slot .output-count.single-digit {
        left: 2rem;
        right: 2rem;
    }

    .item-slot .output-count.multi-digit {
        left: 1rem;
        right: 1rem;
    }

    .item-slot .output-count p {
        font-size: 1.5rem;
        line-height: 2rem;
    }
}

/* md breakpoint (768px and up) */
@media (min-width: 768px) {
    .item-slot {
        width: 4rem;
        height: 4rem;
    }

    .item-slot .output-count {
        top: 1.25rem;
        bottom: 1.25rem;
    }

    .item-slot .output-count.single-digit {
        left: 2.5rem;
        right: 2.5rem;
    }

    .item-slot .output-count.multi-digit {
        left: 1rem;
        right: 1rem;
    }

    .item-slot .output-count p {
        font-size: 2.25rem;
        line-height: 1.5rem;
    }
}
</style>