<script setup lang="ts">
import AppLayout from '@/layouts/AppLayout.vue';
import { type BreadcrumbItem } from '@/types';
import { Head } from '@inertiajs/vue3';
import { Button } from '@/components/ui/button'
import {
    Card,
    CardContent,
    CardDescription,
    CardFooter,
    CardHeader,
    CardTitle,
} from '@/components/ui/card'
import { Input } from '@/components/ui/input'
import { Label } from '@/components/ui/label'
import {
    Select,
    SelectContent,
    SelectItem,
    SelectTrigger,
    SelectValue,
} from '@/components/ui/select'

const breadcrumbs: BreadcrumbItem[] = [
    {
        title: 'Blog',
        href: '/blog',
    },
];

defineProps<{
    name?: string;
}>();
</script>

<template>
    <Head title="Blog" />
    <AppLayout :breadcrumbs="breadcrumbs">
        <div class="flex justify-center h-screen items-center">
            <Card class="w-[350px]">
                <CardHeader>
                    <CardTitle>Create project</CardTitle>
                    <CardDescription>Deploy your new project in one-click.</CardDescription>
                </CardHeader>
                <CardContent>
                    <form>
                        <div class="grid w-full items-center gap-4">
                            <div class="flex flex-col space-y-1.5">
                                <Label for="name">Name</Label>
                                <Input id="name" placeholder="Name of your project" />
                            </div>
                            <div class="flex flex-col space-y-1.5">
                                <Label for="framework">Framework</Label>
                                <Select>
                                    <SelectTrigger id="framework">
                                        <SelectValue placeholder="Select" />
                                    </SelectTrigger>
                                    <SelectContent position="popper">
                                        <SelectItem value="next">
                                            Next.js
                                        </SelectItem>
                                        <SelectItem value="sveltekit">
                                            SvelteKit
                                        </SelectItem>
                                        <SelectItem value="astro">
                                            Astro
                                        </SelectItem>
                                        <SelectItem value="nuxt">
                                            Nuxt
                                        </SelectItem>
                                    </SelectContent>
                                </Select>
                            </div>
                        </div>
                    </form>
                </CardContent>
                <CardFooter class="flex justify-between">
                    <Button variant="outline">
                        Cancel
                    </Button>
                    <Button>Deploy</Button>
                </CardFooter>
            </Card>
        </div>
    </AppLayout>
</template>
