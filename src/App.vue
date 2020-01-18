<template>
  <div class="container-scroller">
    <div class="horizontal-menu">
      <!--  Navbar -->
      <nav class="navbar top-navbar col-lg-12 col-12 p-0">
        <div class="container">
          <div class="navbar-menu-wrapper d-flex align-items-center">
            <ul class="navbar-nav navbar-nav-right">
              <!-- Messages -->
              <Messages />
              <!-- Notifications -->
              <Notifications />
              <!-- User Profile -->
              <UserProfile />
            </ul>
            <button
              class="navbar-toggler navbar-toggler-right d-lg-none align-self-center"
              type="button"
              data-toggle="horizontal-menu-toggle"
            >
              <span class="mdi mdi-menu"></span>
            </button>
          </div>
        </div>
      </nav>
    </div>

    <!-- Main -->
    <div class="container-fluid page-body-wrapper">
      <div class="main-panel">
        <div class="content-wrapper">
          <div class="row">
            <div class="col-md-12 grid-margin">
              <!-- Welcome -->
              <WelcomeMessage />
            </div>
          </div>

          <!-- Pt.1: Graphs -->
          <div class="row">
            <div class="col-xl-6 grid-margin">
              <div class="row">
                <!-- Users -->
                <div class="col-md-6 grid-margin stretch-card">
                  <TotalUsers />
                </div>
                <!-- Projects -->
                <div class="col-md-6 grid-margin stretch-card">
                  <TotalProjects />
                </div>
              </div>

              <!-- Downloads -->
              <div class="row">
              <div class="col-md-12 stretch-card">
                <div class="card">
                  <Downloads />
                </div>
              </div>
              </div>
            </div>

            <!-- TotalSales Chart -->
            <div class="col-xl-6 grid-margin stretch-card">
              <TotalSalesChart />
            </div>
          </div>

          <!-- Pt.2: Monthly totals-->
          <div class="row">
            <!-- Total Sales -->
            <div class="col-md-3 grid-margin stretch-card">
              <div class="card border-0 border-radius-2 bg-success">
                <TotalSales />
              </div>
            </div>

            <!-- Total Purchases -->
            <div class="col-md-3 grid-margin stretch-card">
              <div class="card border-0 border-radius-2 bg-info">
                <TotalPurchases />
              </div>
            </div>

            <!-- Total Orders -->
            <div class="col-md-3 grid-margin stretch-card">
              <div class="card border-0 border-radius-2 bg-danger">
                <TotalOrders />
              </div>
            </div>

            <!-- Total Growth -->
            <div class="col-md-3 grid-margin stretch-card">
              <div class="card border-0 border-radius-2 bg-warning">
                <TotalGrowth />
              </div>
            </div>
          </div>

          <!-- Pt3: Tickets & Updates -->
          <div class="row">
            <div class="col-xl-8 grid-margin stretch-card">
              <!-- Tickets -->
              <Tickets />
            </div>

            <!-- Updates -->
            <div class="col-xl-4 grid-margin stretch-card">
              <Updates />
            </div>
          </div>

          <!-- Pt4: Distribution & Sale Report -->
          <div class="row">
            <div class="col-xl-3 grid-margin stretch-card">
              <!-- Distribution -->
              <Distribution />
            </div>

            <!-- Sale Report -->
            <div class="col-xl-9 grid-margin stretch-card">
              <SaleReport />
            </div>
          </div>

          <!-- Pt5: Invoices -->
          <div class="row">
            <div class="col-md-12">
              <Invoices />
            </div>
          </div>
        </div>

        <!-- Footer -->
        <Footer />
      </div>
    </div>
  </div>
</template>

<script>
import Messages from "./components/Navbar/Messages/Messages";
import Notifications from "./components/Navbar/Notifications/Notifications";
import UserProfile from "./components/Navbar/UserProfile/UserProfile";
import WelcomeMessage from "./components/Main/WelcomeMessage";
import TotalUsers from "./components/Main/TotalUsers";
import TotalProjects from "./components/Main/TotalProjects";
import Downloads from "./components/Main/Downloads";
import TotalSalesChart from "./components/Main/TotalSalesChart";
import TotalSales from "./components/Main/TotalSales";
import TotalPurchases from "./components/Main/TotalPurchases";
import TotalOrders from "./components/Main/TotalOrders";
import TotalGrowth from "./components/Main/TotalGrowth";
import Tickets from "./components/Main/Tickets/Tickets";
import Updates from "./components/Main/Updates/Updates";
import Distribution from "./components/Main/Distribution";
import SaleReport from "./components/Main/SaleReport";
import Invoices from "./components/Main/Invoices/Invoices";
import Footer from "./components/Footer/Footer";



export default {
  name: 'app',
  components: {
    // Navbar
    Messages,
    Notifications,
    UserProfile,
    // Main
    WelcomeMessage,
    TotalUsers,
    TotalProjects,
    Downloads,
    TotalSalesChart,
    TotalSales,
    TotalPurchases,
    TotalOrders,
    TotalGrowth,
    Tickets,
    Updates,
    Distribution,
    SaleReport,
    Invoices,
    // Footer
    Footer
  }
}
</script>

<style>
</style>
