<script setup lang="ts">
import NavFooter from '@/components/NavFooter.vue';
import NavMain from '@/components/NavMain.vue';
import NavUser from '@/components/NavUser.vue';
import { Sidebar, SidebarContent, SidebarFooter, SidebarHeader, SidebarMenu, SidebarMenuButton, SidebarMenuItem } from '@/components/ui/sidebar';
import { type NavItem } from '@/types';
import { Link, usePage } from '@inertiajs/vue3';
import { BookOpen, Folder, LayoutGrid, Users, Shield, Key } from 'lucide-vue-next';
import AppLogo from './AppLogo.vue';

const page = usePage();

// Check if user has permission
const hasPermission = (permission: string): boolean => {
  return page.props.auth.user && 
         page.props.auth.user.permissions && 
         page.props.auth.user.permissions.includes(permission);
};

// Define navigation items with permission checks
const mainNavItems: NavItem[] = [
    {
        title: 'Dashboard',
        href: route('dashboard'),
        icon: LayoutGrid,
    }
];

// Only add Users menu if user has permission
if (hasPermission('view_users')) {
    mainNavItems.push({
        title: 'Users',
        href: route('users.index'),
        icon: Users,
    });
}

// Only add Roles menu if user has permission
if (hasPermission('view_roles')) {
    mainNavItems.push({
        title: 'Roles',
        href: route('roles.index'),
        icon: Shield,
    });
}

// Only add Permissions menu if user has permission
if (hasPermission('view_permissions')) {
    mainNavItems.push({
        title: 'Permissions',
        href: route('permissions.index'),
        icon: Key,
    });
}

const footerNavItems: NavItem[] = [
    {
        title: 'Github Repo',
        href: 'https://github.com/laravel/vue-starter-kit',
        icon: Folder,
    },
    {
        title: 'Documentation',
        href: 'https://laravel.com/docs/starter-kits',
        icon: BookOpen,
    },
];
</script>

<template>
    <Sidebar collapsible="icon" variant="inset">
        <SidebarHeader>
            <SidebarMenu>
                <SidebarMenuItem>
                    <SidebarMenuButton size="lg" as-child>
                        <Link :href="route('dashboard')">
                        <AppLogo />
                        </Link>
                    </SidebarMenuButton>
                </SidebarMenuItem>
            </SidebarMenu>
        </SidebarHeader>

        <SidebarContent>
            <NavMain :items="mainNavItems" />
        </SidebarContent>

        <SidebarFooter>
            <NavFooter :items="footerNavItems" />
            <NavUser />
        </SidebarFooter>
    </Sidebar>
    <slot />
</template>
